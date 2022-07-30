---
title: "Change Directory Python Context Manager"
date: 2022-07-30T17:06:42-04:00
draft: false
description: "Create a context manager in Python that changes working directory"
categories:
  - programming
tags:
  - python
---
I've had this snippet kicking around for a while. I found the basic function
on StackOverflow... somewhere. I cleaned it up a tad, added type annotation,
and present it here to the world.

This content manage allows changing of the current directory temporarily. This
can be useful sometimes if a command needs to be run from a certain directory.

```python
import os
from contextlib import contextmanager
from pathlib import Path
from typing import Generator, Union


@contextmanager
def set_directory(newdir: Union[Path, str]) -> Generator[Path, None, None]:
    """
    Changes the current directory to the given path, within the
    context manager.

    Args:
        newdir: The new path

    Yields:
        old (current) directory, just in case you need it
    """
    olddir = Path().absolute()

    try:
        os.chdir(newdir)
        yield olddir
    finally:
        os.chdir(olddir)
```

In use you'd do something like this:

```python
with set_directory(Path("/buildroot/project")):
    run_build_or_do_something_cool()
```
