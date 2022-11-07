# erc20
ERC-20 Token Standard

The cargo-contract release version used is [v2.0.0-alpha.5](https://github.com/paritytech/cargo-contract/releases/). This release(v2.0.0-alpha.5) supports compatibility with the [v4.0.0-alpha.3](https://github.com/paritytech/ink/releases/tag/v4.0.0-alpha.3) release of [ink!](https://use.ink/4.0.0-alpha.1/).<b><u>It is not backwards compatible with older versions of ink!</u></b>.

Ubuntu 22.04.1 LTS clean install.
```bash
sudo apt install build-essential
sudo apt-get install -y libssl-dev
sudo apt install pkg-config
sudo apt install curl
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustc --version
rustup update
rustup component add rust-src
cargo install cargo-dylint dylint-link
cargo install --force --locked cargo-contract
cargo-contract -V
rustup show
rustup +nightly show
rustup update
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
rustup install nightly-2022-08-15
rustup default nightly
curl https://rustwasm.github.io/wasm-pack/installer/init.sh -sSf | sh
cargo install cargo-contract --version 2.0.0-alpha.5
```








Run the test cases for the  contract
```bash
cargo +nightly test
```

Build the contract
```bash
cargo +nightly contract build
```
In the target folder we should have these files:
```bash
target
  └─ ink
    └─ erc20.contract
    └─ erc20.wasm
    └─ metadata.json
```
A Wasm binary(erc20.wasm), a metadata file (metadata.json/which contains the contract's ABI) and the contract file(erc20.contract/which we will deploy to our chain).

References:<br/>
[ink!](https://use.ink/4.0.0-alpha.1/)<br/>
[Rust and WebAssembly](https://rustwasm.github.io/docs/book/)
