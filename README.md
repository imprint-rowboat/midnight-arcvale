# Midnight Arcvale (Built for Base)

Midnight Arcvale is a browser-first reference repository for Base that confirms network identity (chainId 8453 / 84532) and provides read-only visibility into balances, blocks, and ERC-20 token metadata using Coinbase Wallet SDK plus Base-aligned tooling.

---

## Tooling and dependencies

This repository pulls from both Base and Coinbase open-source ecosystems to keep the workflow aligned with Base account tooling and common developer primitives.

Included components:
- Coinbase Wallet SDK for EIP-1193 wallet access  
- OnchainKit references for Base-aligned primitives and account abstraction workflows  
- viem for fast, typed, read-only RPC communication  
- Multiple Base and Coinbase GitHub repositories referenced directly in package.json  

---

## Repository layout

- app.midnight-arcvale.ts  
  Browser script that renders a minimal UI for wallet connection and read-only Base RPC queries.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - Address.sol — minimal contract for deployment and verification checks  
  - ERC20.sol — simple stateful contract for tracking balances for each address

- config/base.networks.json  
  Static network configuration for Base Mainnet and Base Sepolia (chainIds, RPC URLs, explorers).

- docs/notes.md  
  Short internal notes for maintainers: naming conventions, dependency mapping, and validation checklist.

- package.json  
  Dependency manifest referencing Coinbase SDKs and multiple Base + Coinbase repositories.

- README.md  
  Technical documentation and onchain references.

---

## Base network context

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

---

## Capabilities overview

Midnight Arcvale provides a small, auditable surface for Base diagnostics without sending transactions:

- Connect a Coinbase Wallet and confirm chainId  
- Read ETH balances for arbitrary addresses  
- Fetch latest block metadata (timestamp + gas fields)  
- Run an RPC health check (chainId, block height, gas price)  
- Read ERC-20 token metadata and holder balances via standard view methods  
- Output Basescan references for external verification  

No transactions are signed or broadcast at any stage.

---

## Installation and execution

Install dependencies with Node.js.  
Serve the project with any modern frontend dev server and open it in a browser.

Expected result:
- Active network and chainId displayed  
- Wallet session details visible after connection  
- Read-only balance, block, and ERC-20 data available  
- Basescan links printed for verification  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author

GitHub: https://github.com/imprint-rowboat 

Email: imprint.rowboat.0c@icloud.com 

My twitter: https://x.com/_bienkocree_  

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract Address.sol  address:  
0xf9348714e6bd26266df633aef1d507d391555143

Deployment and verification:
- https://sepolia.basescan.org/address/0xf9348714e6bd26266df633aef1d507d391555143
- https://sepolia.basescan.org/0xf9348714e6bd26266df633aef1d507d391555143/0#code  

Contract ERC20.sol address:  
0x868f1bc9f3a6d3d8bc621fcebc6331c18ab5cc1e

Deployment and verification:
- https://sepolia.basescan.org/address/0x868f1bc9f3a6d3d8bc621fcebc6331c18ab5cc1e
- https://sepolia.basescan.org/0x868f1bc9f3a6d3d8bc621fcebc6331c18ab5cc1e/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
