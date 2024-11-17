# CURRENT

## install fails due to Homebrew conflict

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

## rust no rustc yes

```sh
$ which rust  # rust not found

$ which rustc  # /opt/homebrew/bin/rustc
$ rustc --version  # rustc 1.81.0 (eeb90cda1 2024-09-04) (Homebrew)
```

# SOLUTION

## trade-offs

* port Homebrew pkgs to Rust: screw up configs?
* uninstall Homebrew rustc: existing pkgs unaffected bc already compiled *or* blows up when Homebrew attempts upgrade (could be bad if Homebrew tries to get another Rust compiler)

## plan

* uninstall rustc
* move single pkg from Homebrew to Rust and see what happens
- config files
- `which`
* if successful, move from less important packages to more

## pkg

CORE
* atuin
* bat
* broot
* fd
* eza
* rg

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
