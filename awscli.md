# install

```sh
curl -fsSL https://awscli.amazonaws.com/v2/install.sh | bash
Resolving user-local install paths:
  HOME=/Users/zach
  XDG_DATA_HOME=<unset, using default>
  XDG_BIN_HOME=<unset, using default>
Installing AWS CLI 2.36.16
Downloading AWS CLI installer from https://awscli.amazonaws.com/AWSCLIV2-2.36.16.pkg?src=script-exe
######################################################################## 100.0%
PKG code signature verified (team 94KV3E626L).
installer: Package name is AWS Command Line Interface
installer: choices changes file '/var/folders/j2/z0b166gn4fzfyrlzmjf63bgh0000gn/T/tmp.yuXC5jBh2w/choices.xml' applied
installer: Installing at base path /Users/zach
installer: The install was successful.
AWS CLI 2.36.16 installed to /Users/zach/.local/share/aws-cli
Ensure /Users/zach/.local/bin is on your PATH. When multiple installs exist, PATH order determines which 'aws' runs.

$ aws --version
aws-cli/2.36.16 Python/3.14.6 Darwin/25.2.0 script-exe/arm64
```

# q1

@awscli.md @~/Desktop/install.sh @/Users/zach/Documents/zv/notes/sw/design/system/aws.md @/Users/zach/Documents/zv/notes/sw/guts/operating-systems/denv.md > XDG header

I'd like to redo this install with these set:

- XDG_DATA_HOME
- XDG_BIN_HOME

so that

- I can learn more about how they work
- so that I don't have to update my path

Can you talk me through how that could work?

Also, based on their installer script, how to uninstall?

# a1

## short version

The installer already defaults to:

```sh
XDG_DATA_HOME="$HOME/.local/share"
XDG_BIN_HOME="$HOME/.local/bin"
```

Your first install landed here:

```txt
installed app: /Users/zach/.local/share/aws-cli
symlinks:      /Users/zach/.local/bin/aws
               /Users/zach/.local/bin/aws_completer
```

If you want to avoid updating PATH, set `XDG_BIN_HOME` to a directory that is already on your PATH, probably:

```sh
export XDG_BIN_HOME="/Users/zach/Documents/denv/bin"
```

Then the installer will put only symlinks there, not the full AWS CLI payload.

## how the XDG pieces map

From the installer:

```sh
local data_home="${XDG_DATA_HOME:-$HOME/.local/share}"
local bin_home="${XDG_BIN_HOME:-$HOME/.local/bin}"

INSTALL_DIR="$data_home/aws-cli"
BIN_DIR="$bin_home"
```

So:

```sh
XDG_DATA_HOME=/some/data/root
XDG_BIN_HOME=/some/bin/root
```

becomes:

```txt
/some/data/root/aws-cli       # full AWS CLI install
/some/bin/root/aws            # symlink to installed aws
/some/bin/root/aws_completer  # symlink to installed completer
```

Important: `XDG_DATA_HOME` is for application data. `XDG_BIN_HOME` is not part of the official XDG base-dir spec, but this AWS installer honors it as "where command symlinks go".

## option A: keep data XDG default, use your existing bin

This is the most practical if `/Users/zach/Documents/denv/bin` is already on PATH:

```sh
XDG_BIN_HOME="/Users/zach/Documents/denv/bin" \
  bash /Users/zach/Desktop/install.sh
```

Result:

```txt
/Users/zach/.local/share/aws-cli
/Users/zach/Documents/denv/bin/aws -> /Users/zach/.local/share/aws-cli/aws
/Users/zach/Documents/denv/bin/aws_completer -> /Users/zach/.local/share/aws-cli/aws_completer
```

This teaches the main XDG split:

* data lives under `~/.local/share`
* executable entrypoints live in your bin dir

## option B: put both under denv

If you want everything non-config-ish under `denv`:

```sh
XDG_DATA_HOME="/Users/zach/Documents/denv/share" \
XDG_BIN_HOME="/Users/zach/Documents/denv/bin" \
  bash /Users/zach/Desktop/install.sh
```

Result:

```txt
/Users/zach/Documents/denv/share/aws-cli
/Users/zach/Documents/denv/bin/aws
/Users/zach/Documents/denv/bin/aws_completer
```

This is tidier if you think of `denv` as your local prefix.

## before reinstalling

Your current install is at:

```txt
/Users/zach/.local/share/aws-cli
/Users/zach/.local/bin/aws
/Users/zach/.local/bin/aws_completer
```

If you reinstall with a different `XDG_BIN_HOME`, the old symlinks in `~/.local/bin` may remain. PATH order would then decide which `aws` runs.

Useful checks:

```sh
type -a aws
readlink /Users/zach/.local/bin/aws
readlink /Users/zach/Documents/denv/bin/aws
```

## uninstall based on this installer

For your current user-local install, uninstall is basically removing the install dir plus the symlinks:

```sh
rm -rf /Users/zach/.local/share/aws-cli
rm -f /Users/zach/.local/bin/aws
rm -f /Users/zach/.local/bin/aws_completer
```

If you reinstall with option B, uninstall would be:

```sh
rm -rf /Users/zach/Documents/denv/share/aws-cli
rm -f /Users/zach/Documents/denv/bin/aws
rm -f /Users/zach/Documents/denv/bin/aws_completer
```

Do not remove:

```txt
/Users/zach/.aws
```

That is config/credentials, not the CLI install.

## macOS package receipt caveat

Because the script uses macOS `installer -pkg`, macOS may also have a package receipt. Removing files removes the actual CLI. If you want receipt cleanup too:

```sh
pkgutil --pkgs | grep -i aws
```

Then, if you find the AWS CLI package id, you can forget the receipt with:

```sh
sudo pkgutil --forget <package-id>
```

`pkgutil --forget` does not uninstall files; it only removes the receipt metadata.

# a2

are these the defaults on macOS? on Linux?

```sh
XDG_DATA_HOME="$HOME/.local/share"
XDG_BIN_HOME="$HOME/.local/bin"
```

current output from `echo $XDG_BIN_HOME` is blank i.e. I'm assuming there are no other CLIs on my machine that would be using that, no?

just lob another entry here for now? /Users/zach/Documents/denv/dotfiles/shell/zsh/modules/path.sh

would setting XDG_BIN_HOME for all these create a world in which /Users/zach/Documents/denv/dotfiles/shell/zsh/modules/path.sh wouldn't even be necessary?

zjv, yes - if `/Users/zach/.local/bin` is already on PATH, then the AWS installer's default is already good:

```sh
XDG_BIN_HOME="${XDG_BIN_HOME:-$HOME/.local/bin}"
```

So with `XDG_BIN_HOME` unset, AWS puts symlinks in:

```txt
/Users/zach/.local/bin/aws
/Users/zach/.local/bin/aws_completer
```

and your existing `path.sh` already exposes that.

Your current line appends it:

```sh
export PATH="$PATH:/Users/zach/.local/bin"
```

So if another `aws` exists earlier on PATH, that one wins. Check with:

```sh
type -a aws
```

If you want user-local tools to win over system/Homebrew tools, flip it to prepend:

```sh
export PATH="/Users/zach/.local/bin:$PATH"
```

But if `aws` currently resolves correctly, no need.
