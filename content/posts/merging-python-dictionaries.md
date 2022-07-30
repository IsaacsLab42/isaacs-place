---
title: Merging Python Dictionaries
date: 2022-07-25T18:13:58-04:00
draft: false
summary: Merge dictionaries in Python
categories:
  - programming
tags:
  - python
---
There are many ways to merge Python dictionaries. I'm going to show just two
of the most common ways.

# Merge and Join
The first way will merge the two dictionaries, but alters the first. This
obviously requires fewer objects in memory.

```python
dict1.update(dict2)
```

# Merge and Create New 

This will merge python dictionaries without changing either one. This is
useful when you want to preserve the contents of both and create a 3rd.

```python
def merge_dict(dict1, dict2):
    """
    Merge the contents of two dictionaries together and create a 3rd
    dictionary. Items in dict1 with the same name as items in dict2
    will be overridden. i.e. dict2 wins.
    
    Args:
        dict1: First dictionary of items
        dict2: Second dictionary of items. This one wins in the
            situation where both dictionaries have the same key name.
    
    Returns:
        Combined dictionary
    """
    # This works by expanding each dict into (key, value) pairs
    merged = {**dict1, **dict2}
    return merged
```
