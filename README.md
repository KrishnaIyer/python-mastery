# Python Mastery

This codebase contains Python learnings and snippets.

## Installing Python

macOS is bundled with a default Python3 version. This version is usually far behind the [latest stable version](https://www.python.org/downloads/macos/).

But, this is used by the OS and this is not recommended to mess with.

```bash
~ » which python3
/usr/bin/python3

~ » python3 --version
Python 3.9.6
```

Instead, install Python using Homebrew

```bash
$ brew install python
```

This gets installed to `/opt/homebrew/bin/python3`.

We can symlink this as `python` (without appending the version number). This makes it easier to separate the installations and upgrade it when necessary.

```bash
alias python=/opt/homebrew/bin/python3
```

Now check if Python was properly installed.

```bash
~ » which python
python: aliased to /opt/homebrew/bin/python3
~ » python --version
Python 3.14.0
```
