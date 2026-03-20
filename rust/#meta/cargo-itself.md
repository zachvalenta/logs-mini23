## 2026-03-17 — triggered by room rust-toolchain.toml (channel = "stable")

```sh
$ cd /tmp/room && cargo build --release --target wasm32-wasip1
# rust-toolchain.toml required stable, which was 1.94.0 — updated from 1.92.0
info: syncing channel updates for 'stable-aarch64-apple-darwin'
info: latest update on 2026-03-05, rust version 1.94.0 (4a4ef493e 2026-03-02)
# ... installed 1.94.0
```

## 2025-06-26

$ rustup update

info: syncing channel updates for 'stable-aarch64-apple-darwin'
info: latest update on 2025-06-26, rust version 1.88.0 (6b00bc388 2025-06-23)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
info: downloading component 'rust-std'
info: downloading component 'rustc'
 60.4 MiB /  60.4 MiB (100 %)  16.9 MiB/s in  3s ETA:  0s
info: downloading component 'rustfmt'
info: removing previous version of component 'cargo'
info: removing previous version of component 'clippy'
info: removing previous version of component 'rust-docs'
info: removing previous version of component 'rust-std'
info: removing previous version of component 'rustc'
info: removing previous version of component 'rustfmt'
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 20.1 MiB /  20.1 MiB (100 %)   6.9 MiB/s in  1s ETA:  0s
info: installing component 'rust-std'
 25.0 MiB /  25.0 MiB (100 %)  20.9 MiB/s in  1s ETA:  0s
info: installing component 'rustc'
 60.4 MiB /  60.4 MiB (100 %)  22.9 MiB/s in  2s ETA:  0s
info: installing component 'rustfmt'
info: checking for self-update
info: downloading self-update

  stable-aarch64-apple-darwin updated - rustc 1.88.0 (6b00bc388 2025-06-23) (from rustc 1.83.0 (90b35a623 2024-11-26))

info: cleaning up downloads & tmp directories
