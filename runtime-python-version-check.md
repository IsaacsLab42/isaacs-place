```python
import sys

if sys.version_info < (3, 8):  # or whatever version
    raise RuntimeError("This script requires Python 3.8 or higher")
```
