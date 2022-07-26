---
title: "Python Runtime Version Check"
date: 2022-07-26T14:30:20-04:00
draft: false
categories:
  - programming
tags:
  - python
---
Okay, so this is easy to find anywhere on the internet, but I am posting this
here for my reference. Most of my scripts are fairly version insensitive, so
I don't use this often enough to actually commit it to memory.

```python
import sys

if sys.version_info < (3, 8):  # or whatever version
    raise RuntimeError("This script requires Python 3.8 or higher")
```
