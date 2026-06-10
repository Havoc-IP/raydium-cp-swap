# raydium-cp-swap

A revamped constant product AMM program optimized for straightforward pool deployment along with additional features and integrations:
- No Openbook market ID is required for pool creation
- Token22 is supported
- Built-in price oracle
- Optimized in Anchor

The program has been audited by [MadShield](https://www.madshield.xyz/). The report can be found [here](https://github.com/raydium-io/raydium-docs/tree/master/audit/MadShield%20Q1%202024).

The program assets are in-scope for Raydium’s [Immunefi bug bounty program](https://immunefi.com/bug-bounty/raydium/).

## Environment Setup

1. Install Dependencies

   ```shell
   sudo apt-get update && sudo apt-get install -y pkg-config build-essential libudev-dev libssl-dev llvm libclang-dev protobuf-compiler
   ```

2. Install Rust Toolchain
   ```shell
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh source $HOME/.cargo/env
   ```
   
3. Install Solana CLI (v2.3.5)
   ```shell
   sh -c "$(curl -sSfL https://release.anza.xyz/v2.3.5/install)" echo 'export PATH="$HOME/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc source ~/.bashrc   
   ```
4. Install Anchor Version Manager 
   ```shell  
   cargo install --git https://github.com/coral-xyz/anchor avm --locked --force echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc source ~/.bashrc      
   ```
5. Install Project Specfic Version
   ```shell
   avm install 0.32.1
   avm use 0.32.1
   ```
6. Set proper environment  
   ```shell
   rm -rf target Cargo.lock
   agave-install init 2.3.5
   ```
7. Check versions 
   ```shell
   cargo-build-sbf --version
   ```
## Should produce    
   solana-cargo-build-sbf 2.3.5
   platform-tools v1.48
   rustc 1.84.1

8. Build
   ```shell
      anchor build 
   ```   

ORIGINAL 
   

1. Install `Rust`

   ```shell
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   rustup default 1.81.0
   ```

2. Install `Solana `

   ```shell
   sh -c "$(curl -sSfL https://release.anza.xyz/v2.1.0/install)"
   ```

   then run `solana-keygen new` to create a keypair at the default location.

3. install `Anchor`

   ```shell
   # Installing using Anchor version manager (avm) 
   cargo install --git https://github.com/coral-xyz/anchor avm --locked --force
   # Install anchor
   avm install 0.31.0
   ```

## Quickstart

Clone the repository and test the program.

```shell

git clone https://github.com/raydium-io/raydium-cp-swap
cd raydium-cp-swap && yarn && anchor test
```

## License

Raydium constant product swap is licensed under the Apache License, Version 2.0.
