# CURRENT

## install fails due to Brew conflict

```sh
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

info: downloading installer
warning: it looks like you have an existing installation of Rust at:
warning: /opt/homebrew/bin
warning: It is recommended that rustup be the primary Rust installation.
warning: Otherwise you may have confusion unless you are careful with your PATH
warning: If you are sure that you want both rustup and your already installed Rust
warning: then please reply `y' or `yes' or set RUSTUP_INIT_SKIP_PATH_CHECK to yes
warning: or pass `-y' to ignore all ignorable checks.
error: cannot install while Rust is installed
Continue? (y/N) N
error: cannot install while Rust is installed
```

## ❌ rust/rustup ✅ cargo/rustc

```sh
$ which rust  # rust not found
$ which rustup  # rustup not found

$ which rustc  # /opt/homebrew/bin/rustc
$ rustc --version  # rustc 1.81.0 (eeb90cda1 2024-09-04) (Homebrew)
$ which cargo  # /opt/homebrew/bin/cargo
$ cargo version  # cargo 1.81.0

$ ls /opt/homebrew/bin | rg rust  # rust-gdb rust-gdbgui rust-lldb rustc rustdoc

$ brew info rust  # rustup not installed, cargo/rustc err for brew info
==> rust: stable 1.81.0 (bottled), HEAD
Installed
/opt/homebrew/Cellar/rust/1.81.0 (3,435 files, 312.3MB) *
  Poured from bottle using the formulae.brew.sh API on 2024-10-27 at 20:31:59
From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/r/rust.rb
==> Dependencies
Required: libgit2 ✔, libssh2 ✔, llvm ✔, openssl@3 ✔, pkg-config ✔, zstd ✔
==> Requirements
Required: macOS >= 10.12 (or Linux) ✔
==> Caveats
zsh completions have been installed to:
  /opt/homebrew/share/zsh/site-functions
```

# SOLUTION

## trade-offs

* port Homebrew pkgs to Rust: screw up configs?
* uninstall Homebrew rustc: existing pkgs unaffected bc already compiled *or* blows up when Homebrew attempts upgrade (could be bad if Homebrew tries to get another Rust compiler)

## uninstall Rust

```sh
$ brew uninstall rust

Uninstalling /opt/homebrew/Cellar/rust/1.81.0... (3,435 files, 312.3MB)
==> Autoremoving 2 unneeded formulae:
llvm
z3
Uninstalling /opt/homebrew/Cellar/llvm/18.1.8... (7,722 files, 1.8GB)
Uninstalling /opt/homebrew/Cellar/z3/4.13.0... (120 files, 31.5MB)

$ which rust  # rust not found
$ which rustup  # rustup not found
$ which rustc  # rustc not found
$ which cargo  # cargo not found

$ ls /opt/homebrew/bin | rg rust  # nada

$ brew info rust
==> rust: stable 1.81.0 (bottled), HEAD
Not installed
From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/r/rust.rb
==> Dependencies
Required: libgit2 ✔, libssh2 ✔, llvm ✘, openssl@3 ✔, pkg-config ✔, zstd ✔
==> Requirements
Required: macOS >= 10.12 (or Linux) ✔
```

## check pkgs still work

CORE
* ✅ atuin
* ✅ bat
* ✅ broot
* ✅ fd
* ✅ eza
* ✅ rg

LITTLE UTILS
* basilk
* mdcat
* dust / procs / havn
* monolith
* onefetch
* pastel
* tokei

DEV
* hexyl
* serie / delta
* zola

## install Rust

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
info: downloading installer

Welcome to Rust!

This will download and install the official compiler for the Rust
programming language, and its package manager, Cargo.

Rustup metadata and toolchains will be installed into the Rustup
home directory, located at:

  /Users/zach/.rustup

This can be modified with the RUSTUP_HOME environment variable.

The Cargo home directory is located at:

  /Users/zach/.cargo

This can be modified with the CARGO_HOME environment variable.

The cargo, rustc, rustup and other commands will be added to
Cargo's bin directory, located at:

  /Users/zach/.cargo/bin

This path will then be added to your PATH environment variable by
modifying the profile files located at:

  /Users/zach/.profile
  /Users/zach/.zshenv

You can uninstall at any time with rustup self uninstall and
these changes will be reverted.

Current installation options:


   default host triple: aarch64-apple-darwin
     default toolchain: stable (default)
               profile: default
  modify PATH variable: yes

1) Proceed with standard installation (default - just press enter)
2) Customize installation
3) Cancel installation
>1

info: profile set to 'default'
info: default host triple is aarch64-apple-darwin
info: syncing channel updates for 'stable-aarch64-apple-darwin'
info: latest update on 2024-10-17, rust version 1.82.0 (f6e511eec 2024-10-15)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
 16.3 MiB /  16.3 MiB (100 %)  12.6 MiB/s in  1s ETA:  0s
info: downloading component 'rust-std'
 23.4 MiB /  23.4 MiB (100 %)   8.3 MiB/s in  2s ETA:  0s
info: downloading component 'rustc'
 54.7 MiB /  54.7 MiB (100 %)  10.3 MiB/s in  5s ETA:  0s
info: downloading component 'rustfmt'
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 16.3 MiB /  16.3 MiB (100 %)   6.7 MiB/s in  1s ETA:  0s
info: installing component 'rust-std'
 23.4 MiB /  23.4 MiB (100 %)  20.7 MiB/s in  1s ETA:  0s
info: installing component 'rustc'
 54.7 MiB /  54.7 MiB (100 %)  22.7 MiB/s in  2s ETA:  0s
info: installing component 'rustfmt'
info: default toolchain set to 'stable-aarch64-apple-darwin'

  stable-aarch64-apple-darwin installed - rustc 1.82.0 (f6e511eec 2024-10-15)


Rust is installed now. Great!

To get started you may need to restart your current shell.
This would reload your PATH environment variable to include
Cargo's bin directory ($HOME/.cargo/bin).

To configure your current shell, you need to source
the corresponding env file under $HOME/.cargo.

This is usually done by running one of the following (note the leading DOT):
. "$HOME/.cargo/env"            # For sh/bash/zsh/ash/dash/pdksh
source "$HOME/.cargo/env.fish"  # For fish
```
```sh
$ . "$HOME/.cargo/env"
$ rust --version # zsh: command not found: rust

$ cargo --version  # cargo 1.82.0 (8f40fc59f 2024-08-21)
$ rustc --version  # rustc 1.82.0 (f6e511eec 2024-10-15)
```

## port from Brew to Rust

* move single pkg from Homebrew to Rust and see what happens
- config files
- `which`
* if successful, move from less important packages to more
