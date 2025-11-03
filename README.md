# Python Mastery

This codebase contains Python learnings and snippets.

## Installing Python

macOS is bundled with a default Python3 version. This version is usually far behind the [latest stable version](https://www.python.org/downloads/macos/).

```bash
~ » which python3
/usr/bin/python3

~ » python3 --version
Python 3.9.6
```

But, this is used by the OS and this is not recommended to mess with.

The recommended way is to use `uv` to install Python per project in the `venv` (virtual environment). This helps separate dependencies. If you really want to install a global python, check out the [guide below](./README.md#installing-global-python-not-recommended)

[`uv`](https://docs.astral.sh/uv) is a modern, fast package manager, written in Rust.

```bash
$ brew install uv
$ which uv
/opt/homebrew/bin/uv
```

`uv` uses `pyproject.toml` to configure projects.

## Creating a New Project

Navigate to the required folder. Create one for the project if necessary.

```bash
$ cd <project>
```

Create a `venv` with the required Python version. If this version is not found globally, this will be installed for the venv.

```bash
$ uv venv --python 3.14.0
```

Now initialize `uv`

```bash
$ uv init
```

Check in `.python-version` and `pyproject.toml` that the correct `major.minor` version is configured.

## Setting Up Essential Tools

### 1. Linter and Formatter

[`ruff`](https://docs.astral.sh/ruff/tutorial/) is a great modern linter and formatter.

From the project folder.

```bash
$ cd <project>
```

Add `ruff`

```bash
$ uv add ruff
```

This tags the value in `uv.lock`, which can be checked in to version control.

[Configure](https://docs.astral.sh/ruff/configuration/) it based on the requirements.

## Appendix

### Installing Global Python (not recommended)

You can use `Homebrew` to install Python globally.

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
