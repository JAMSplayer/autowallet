# AutoWallet - Autonomi Application Framework

<img width="1106" alt="autowallet-promo-light" src="https://github.com/user-attachments/assets/0e7087df-5036-4f06-b011-a6635a11cdd2" />

## Getting Started

Wiki coming soon on all the features!

### Developers

-   System libraries and Rust: https://v2.tauri.app/start/prerequisites/

-   Download Rust dependencies.

### Frontend

1. Node.js and npm/yarn

1. **Install Node modules**:  
   Run the following command in your terminal:

    ```bash
    yarn install

    ```

2. **Run Tauri App**:  
   Run the following command in your terminal:
    ```bash
    yarn run tauri dev
    ```
    
3. **Build Tauri App for Production**:  
   Run the following command in your terminal:

    ```bash
    yarn run tauri build

    ```



Side-note: If you wish to run the development web server (if you for some reason don't want to run it via tauri):

```bash
yarn run dev

```

### Icon Generation

To generate the icons for the project run:

```
cargo tauri icon public/icon-gen.png
```

### WARNING

AutoWallet is in active development, please only use testnet funds, or if using mainnet, small amounts!


### Network

-   Connecting to a network isn't required at the moment to run the app, but you can run a local testnet:

https://github.com/maidsafe/safe_network/blob/main/README.md#Using-a-local-network

-   Connect to local testnet:

Edit `await invoke("connect", [...]` line in `connect()` function in `src/backend/autonomi.tsx` file, and replace `peer` value with one of your local nodes' Multiaddress, which can be found in node logs. You can see where logs are stored when starting local network, the startup process will output something like "Logging to directory: [...]". In the logfile you search for the line looking like this: `Local node is listening ListenerId(1) on "/ip4/127.0.0.1/udp/11111/quic-v1/p2p/AaaAaa11AaaAaa11AaaAaa11AaaAaa11AaaAaa11AaaAaa11AaaA"`. Address can also be checked running this command:

`cargo run --release --bin safenode-manager --features local -- local status --details`

-   (alternatively) Connecting to official testnet:

Same as above, but instead local node's Multiaddr in `peer`, just insert something that is not Multiaddr, or leave it empty.
