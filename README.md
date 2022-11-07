# erc20
[ERC-20 Token Standard](https://eips.ethereum.org/EIPS/eip-20)

The cargo-contract release version used is [v2.0.0-alpha.5](https://github.com/paritytech/cargo-contract/releases/). This release(v2.0.0-alpha.5) supports compatibility with the [v4.0.0-alpha.3](https://github.com/paritytech/ink/releases/tag/v4.0.0-alpha.3) release of [ink!](https://use.ink/4.0.0-alpha.1/).<b>It is not backwards compatible with older versions of ink!</b>.

Setup for Ubuntu 22.04.1 LTS clean install.
```bash
sudo apt install build-essential
sudo apt-get install -y libssl-dev
sudo apt install pkg-config
sudo apt install curl
sudo apt update
sudo apt upgrade
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustup update
rustup component add rust-src
cargo install cargo-dylint dylint-link
cargo install --force --locked cargo-contract
rustup update
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
rustup install nightly-2022-08-15
rustup default nightly
cargo install cargo-contract --version 2.0.0-alpha.5
```

The environment should look like this.
```bash
rustc --version
```
![image](https://user-images.githubusercontent.com/76512851/200311825-aa4d05c7-075c-45c5-896f-d1aaee15d592.png)

```bash
rustup show
```
![image](https://user-images.githubusercontent.com/76512851/200315230-ecb0a90c-38a8-45e5-aaa3-0f474397ce2f.png)

```bash
rustup +nightly show
```
![image](https://user-images.githubusercontent.com/76512851/200316327-b289a3aa-4a7c-41d9-ac38-a044fc7bfbb1.png)

```bash
cargo-contract -V
```
![image](https://user-images.githubusercontent.com/76512851/200310950-d5a5e787-5e43-4096-9453-758b42d03f53.png)
<hr/>

[Run the test cases for the contract.](https://use.ink/4.0.0-alpha.1/getting-started/creating-an-ink-project#testing-your-contract)

```bash
cargo +nightly test
```

[Compile the contract.](https://use.ink/4.0.0-alpha.1/getting-started/building-your-contract)

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

[Deploy the contract](https://use.ink/4.0.0-alpha.1/getting-started/deploy-your-contract)

References:<br/>
[ink!](https://use.ink/4.0.0-alpha.1/)<br/>
[Rust and WebAssembly](https://rustwasm.github.io/docs/book/)
