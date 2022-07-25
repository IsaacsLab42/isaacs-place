This merges two python dictionaries, but alters the first dictionary:

```python
dict1.update(dict2)
```

Merges python dictionaries without changing either one. This is useful when you want to
preserve the contents of both and create a 3rd.

```python
def merge_dict(dict1, dict2):
    """
    Merge the contents of two dictionaries together and create a 3rd dictionary.
    Items in dict1 with the same name as items in dict2 will be overridden.
    i.e. dict2 wins.
    
    Args:
        dict1: First dictionary of items
        dict2: Second dictionary of items. This one wins in the situation where both
            dictionaries have the same key name.
    
    Returns:
        Combined dictionary
    """
    # This works by expanding each dict into (key, value) paiurs
    merged = {**dict1, **dict2}
    return merged
```
