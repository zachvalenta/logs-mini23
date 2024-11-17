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
```

## port from Brew to Rust

* move single pkg from Homebrew to Rust and see what happens
- config files
- `which`
* if successful, move from less important packages to more
