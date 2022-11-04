# erc20
ERC-20 Token Standard

It's assumed that Rust is [configured and running](https://doc.rust-lang.org/cargo/getting-started/installation.html).

It's assumed that ink! CLI is [configured and running](https://use.ink/4.0.0-alpha.1/getting-started/setup#ink-cli)

```bash
cargo-contract
```
![image](https://user-images.githubusercontent.com/76512851/200001258-5d3bb9ab-ea23-44f7-b93b-f38333e4bb4b.png)

Run the test cases for the  contract
```bash
cargo +nightly test
```

Build the contract
```bash
cargo +nightly contract build
```

target
  └─ ink
    └─ erc20.contract
    └─ erc20.wasm
    └─ metadata.json


References:<br/>
[ink!](https://use.ink/4.0.0-alpha.1/)<br/>
[Rust and WebAssembly](https://rustwasm.github.io/docs/book/)
