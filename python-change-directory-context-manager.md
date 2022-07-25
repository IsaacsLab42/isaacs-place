This content manage allows changing of the current directory temporarily. This
can be useful sometimes if a command needs to be run from a certain directory.

```python
import os
from contextlib import contextmanager
from pathlib import Path

@contextmanager
def set_directory(path):
    """
    Set the cwd within the context
    
    Args:
        path (Path): The new path
    
    Yields:
        old cwd
    """
    origin = Path().absolute()
    
    try:
        os.chdir(path)
        yield origin
    finally:
        os.chdir(origin)
```

In use you'd do something like this:

```python
with set_directory(Path("/tmp")):
    run_build()
```
