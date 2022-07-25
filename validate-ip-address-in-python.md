```python
import ipaddress
def valid_ip(address: str) -> bool:
    """
    Validate the the given string represent an IP address.
    
    Args:
        address: IP address string to validate
    
    Returns:
        True if the string contains a valid IP address. False otherwise.
    """
    retval: bool = True
    
    try:
        _ip = ipaddress.ip_address(address)
    except ValueError:
        retval = False
    
    return retval
```
