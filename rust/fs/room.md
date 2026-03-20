💻 📍 commit hash
🗄️
* `tools/os/multiplexers.md`
* `denv/logs/rust/#meta/rust-itself.md`
* `denv/logs/rust/#meta/cargo-itself.md`

# init

```sh
curl -L "https://github.com/rvcas/room/releases/latest/download/room.wasm" -o ~/.config/zellij/plugins/room.wasm
```

# problem

* `room` 1.2.1 was built against `zellij-tile` 0.41
* you have `zellij` 0.43.1 installed
* `zellij-tile` 0.41 incompatible w/ `zellij` 0.43.1

# further explanation

* Zellij plugins compile to WebAssembly against zellij-tile, which is a Rust crate that defines the plugin API.
* Zellij's plugin API is not stable. When Zellij releases a new version, that API can change and any plugin compiled against an older zellij-tile may silently fail against a newer Zellij runtime.
* Every time Zellij cuts a minor release, plugin authors have to bump zellij-tile, recompile, and ship a new binary. Plugins that aren't actively maintained or just haven't caught up break silently.

# fix 26.03.17 — rebuild room against zellij-tile 0.43.1

```sh
gh repo clone rvcas/room /tmp/room
# edit /tmp/room/Cargo.toml: zellij-tile = "0.41" -> "0.43.1"
rustup target add wasm32-wasip1  # logged in #meta/rust-itself.md
cargo build --release --target wasm32-wasip1  # rebuild room + also updated Rust 1.92->1.94 via rust-toolchain.toml
cp /tmp/room/target/wasm32-wasip1/release/room.wasm ~/.config/zellij/plugins/room.wasm
```
