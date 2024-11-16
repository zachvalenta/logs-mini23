# install fails due to Homebrew conflict
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

# no pkg rely on rust

```sh
$ brew uses --installed python # cairo, cmus, ffmpeg, glib, harfbuzz, libass, llvm, pango, rust, tesseract, yt-dlp
$ brew uses --installed rust # no output
```

# Homebrew has rustc

```sh
$ which rustc  # /opt/homebrew/bin/rustc
$ rustc --version  # rustc 1.81.0 (eeb90cda1 2024-09-04) (Homebrew)
```
