```python
import zlib
from typing import BinaryIO

def file_crc32(fp: BinaryIO, offset: int = 0, size: int = 0, chunksize: int = 65536) -> int:
    """
    Calculate the CRC32 from file-based contents.
    
    The reads the given file in chunks, which avoids the memory overhead of reading
    an entire file at once. This also allows the optional specification of a file
    offset and data length. This allows the calculation of CRC32 over just a portion
    of a file. This may be useful if a file contains individual records, for example.
    
    By default the CRC32 of the entire file is calculated. For example:
    
        filename = "myfile.dat"
        with open(filename, "rb") as fp:
            crc = file_crc32(fp)
        print(f"The CRC32 of {filename} is 0x{crc:08x}")
    
    Warning: This requires Python 3.8 or higher.
    
    Args:
        fp: File that has been opened for reading in binary mode
        offset: File offset from which to start
        size: Number of bytes to include in the CRC32 calculation
        chunksize: Size of the chunks to read at a time, so that the whole file is
            not read all at once.
    
    Returns:
        Calculated CRC32
    """
    fp.seek(offset)
    
    if size != 0:
        chunksize = min(size, chunksize)
        remaining = size
    else:
        remaining = 0xffffffff
    
    checksum: int = 0
    while (chunk := fp.read(chunksize)) and remaining != 0:
        checksum = zlib.crc32(chunk, checksum)
        if size != 0:
            remaining -= len(chunk)
            chunksize = min(remaining, chunksize)
    
    return checksum
```
