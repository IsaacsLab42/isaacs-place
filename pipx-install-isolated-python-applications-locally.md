# pipx -- Install Isolated Python Applications Locally
## What?
`pipx` allows you to install and run Python applications in isolated environments. This is great
for at least a couple of reasons. One, dependencies between different scripts will never interfere
with each other. Two, applications can be installed locally and not globally as root.

## Install
As a normal (non-root) user install `pipx` by using `pip`. Note that this requires `pip` to already
be installed and configured.

```bash
python3 -m pip install --user pipx
```

That will install pipx under the `$HOME/.local/bin` directory. Make sure this directory has been
added to your path.

## Use
If there is a Python application/script that you find yourself using often, and don't want to
install it system-wide, then use `pipx`. For example, the Python code formatter is a pretty
common package that you may want to have access to universally.

```bash
$ pipx install black
  install package black 22.3.0, installed using Python 3.10.0
  These apps are now globally available
    - black
    - blackd
done!
```
The above creates a virtual environment for `black` which contains it's dependencies and only it's dependencies.
