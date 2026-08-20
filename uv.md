# uv itself

```
$ curl -LsSf https://astral.sh/uv/install.sh | sh

downloading uv 0.12.5 aarch64-apple-darwin
installing to /Users/zach/.local/bin
  uv
  uvx
everything's installed!
```

# verify existing Python runtimes

```sh
which python  # /Users/zach/.pyenv/shims/python

uv python list
cpython-3.15.0rc1-macos-aarch64-none                 <download available>
cpython-3.15.0rc1+freethreaded-macos-aarch64-none    <download available>
cpython-3.14.7-macos-aarch64-none                    <download available>
cpython-3.14.7+freethreaded-macos-aarch64-none       <download available>
cpython-3.13.15-macos-aarch64-none                   <download available>
cpython-3.13.15+freethreaded-macos-aarch64-none      <download available>
cpython-3.13.7-macos-aarch64-none                    /opt/homebrew/bin/python3.13 -> ../Cellar/python@3.13/3.13.7/bin/python3.13
cpython-3.13.7-macos-aarch64-none                    /opt/homebrew/bin/python3 -> ../Cellar/python@3.13/3.13.7/bin/python3
cpython-3.12.14-macos-aarch64-none                   <download available>
cpython-3.12.6-macos-aarch64-none                    /opt/homebrew/bin/python3.12 -> ../Cellar/python@3.12/3.12.6/bin/python3.12
cpython-3.12.1-macos-aarch64-none                    /Users/zach/.pyenv/shims/python3.12
cpython-3.12.1-macos-aarch64-none                    /Users/zach/.pyenv/shims/python3
cpython-3.12.1-macos-aarch64-none                    /Users/zach/.pyenv/shims/python
cpython-3.11.16-macos-aarch64-none                   <download available>
cpython-3.10.21-macos-aarch64-none                   <download available>
cpython-3.9.25-macos-aarch64-none                    <download available>
cpython-3.9.6-macos-aarch64-none                     /usr/bin/python3
cpython-3.8.20-macos-aarch64-none                    <download available>
pypy-3.11.15-macos-aarch64-none                      <download available>
pypy-3.10.16-macos-aarch64-none                      <download available>

uv run python --version  # Python 3.9.6

uv run python -c "import sys; print(sys.executable)" # /Library/Developer/CommandLineTools/usr/bin/python3
```

# 3.14

```sh
uv python dir  # /Users/zach/.local/share/uv/python

uv python install 3.14 # Installed Python 3.14.7 in 1.59s + cpython-3.14.7-macos-aarch64-none (python3.14)

# /Users/zach/.local/share/uv
drwxr-xr-x@ -  .
drwxr-xr-x@ - └──  python
.rw-r--r--@ 1     ├── 󰊢 .gitignore
.rw-rw-rw-@ 0     ├──  .lock
drwxr-xr-x@ -     ├──  .temp
lrwxr-xr-x@ -     ├──  cpython-3.14-macos-aarch64-none -> /Users/zach/.local/share/uv/python/cpython-3.14.7-macos-aarch64-none
drwxr-xr-x@ -     └──  cpython-3.14.7-macos-aarch64-none
```

# venv, verify ssl/lzma

```sh
pwd      # /Users/zach/Documents/zv/projects/ml/source-iq
eza -al  # nada

uv venv --python 3.14

# Using CPython 3.14.7
# Creating virtual environment at: .venv
# Activate with: source .venv/bin/activate

uv run python -c "import ssl, lzma; print('ok')"  # ok

uv run python -c "import sys; print(sys.executable)" # /Users/zach/Documents/zv/projects/ml/source-iq/.venv/bin/python3
uv run python --version  # Python 3.14.7
```
