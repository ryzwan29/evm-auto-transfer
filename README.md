# EVM Auto Transfer

Welcome to the `evm-auto-transfer` repository! This script allows you to automate transactions across multiple EVM-compatible networks. Whether you're interacting with testnets or mainnets, this tool simplifies the process, especially for tasks requiring multiple transfers.

## Features

- 📡 Dynamic RPC URL, chain ID, and explorer integration from JSON files.
- 🔄 Automated transaction processing for multiple addresses.
- 🎯 Targeted transfers to specified addresses from `addresses.json`.
- 🚀 Easily configurable for various networks (testnets and mainnets).
- 🔒 Secure handling of private keys.

# Installation
```
source <(curl -s https://raw.githubusercontent.com/ryzwan29/evm-auto-transfer/main/quick-installation.sh)
```

### Configuration

1. **Define the Chains**:

   - You'll need to specify the network details in JSON files located in the `/chains` directory. Create two JSON files: `testnet.json` and `mainnet.json`.
   - Each file should contain an array of objects with the following structure:

     ```json
     [
         {
             "name": "Network Name",
             "rpcUrl": "https://rpc-url",
             "chainId": "1234",
             "symbol": "TOKEN",
             "explorer": "https://explorer-url"
         }
     ]
     ```

   - Example for `testnet.json`:

     ```json
     [
         {
             "name": "Plume Testnet",
             "rpcUrl": "https://plume-testnet-rpc.example.com",
             "chainId": "8888",
             "symbol": "PLUME",
             "explorer": "https://plume-testnet-explorer.example.com"
         }
     ]
     ```

2. **Define Private Keys**:

   - Store your private keys securely inside a `privateKeys.json` file in the root directory. This file should contain an array of private keys as strings:

     ```json
     [
         "0xYOUR_PRIVATE_KEY_1",
         "0xYOUR_PRIVATE_KEY_2"
     ]
     ```

     **⚠️ Important**: Keep this file secure and avoid exposing your private keys!

3. **Create Target Addresses File**:

   - Create an `addresses.json` file in the root directory. This file should contain an array of target addresses you want to transfer funds to:

     ```json
     [
         "0xTARGET_ADDRESS_1",
         "0xTARGET_ADDRESS_2"
     ]
     ```

### Usage

1. Run the script for random address generation and transactions:

   ```bash
   npm start
   ```

2. To use the targeted address feature, run:

   ```bash
   npm run target
   ```

   - You will be prompted to select your network environment (Testnet/Mainnet) and choose the chain from the provided list using the arrow keys.
   - Define the number of transactions you want to process and let the script handle the rest!
