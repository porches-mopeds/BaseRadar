# BaseRadar (Built for Base)

Deployed on Base Mainnet.

Base Radar is a browser-first reference project that continuously inspects Base network state using read-only RPC calls. It is designed to validate wallet connectivity, chain targeting, and Base tooling compatibility in account abstraction–ready environments.

---

## Base ecosystem alignment

Built for Base.

Supported networks:
- Base Mainnet  
  chainId (decimal): 8453  
  Explorer: https://basescan.org  

- Base Sepolia  
  chainId (decimal): 84532  
  Explorer: https://sepolia.basescan.org  

The application explicitly targets Base networks and relies on official Base RPC endpoints.

---

## What the script does

The app.base-radar.ts script provides an in-browser interface that:

1) Connects a wallet using Coinbase Wallet SDK  
2) Reads and validates the active chainId  
3) Performs read-only Base RPC queries:
   - latest block number  
   - ETH balance of the connected address  
4) Emits a “block signal” snapshot (block number, timestamp, gas usage)  
5) Allows ETH balance checks for arbitrary addresses  
6) Prints Basescan links for verification  

No transactions are sent. All interactions are strictly read-only.

---

## Repository structure

- app.base-radar.ts  
  Browser-based script that connects to a wallet, toggles Base networks, and inspects live onchain signals.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - contract.sol — minimal smart contract that performs safe addition and subtraction with overflow and underflow checks  
  - structs.sol — demonstrating struct usage, mappings, and basic CRUD operations for user-owned data
  - errors.sol — lightweight contract demonstrating error handling, arithmetic logic, and safe array operations  

- package.json  
  Dependency manifest including Coinbase SDKs and 2–5 repositories from the Base GitHub organization.

- README.md  
  Technical documentation, Base references, licensing, and testnet deployment records.

---

## Libraries used

- @coinbase/wallet-sdk  
  Wallet connection layer compatible with Coinbase tooling and Base accounts.

- viem  
  RPC client used for Base reads and block inspection.

- Coinbase GitHub repositories  
  Included as dependencies to reference the broader Coinbase open-source ecosystem.

- Base GitHub repositories  
  Included as dependencies to document linkage with Base tooling and infrastructure.

---

## Installation and execution

Install dependencies using Node.js.  
Serve the project with a modern frontend dev server and open the page in a browser.

Expected result:
- Connected address printed with Basescan link  
- Active chainId displayed (8453 or 84532)  
- Read-only Base RPC data displayed  
- Block signal snapshot available on demand  

---

## License

MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author

GitHub: https://github.com/porches-mopeds  
Email: porches.mopeds.0v@icloud.com  
Public contact: https://x.com/LabrancheAmelie  

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract "contract" address:  
0x7e3abceb11f99e67d034154d125f80f4ecb2f376

Deployment and verification:
- https://sepolia.basescan.org/address/0x7e3abceb11f99e67d034154d125f80f4ecb2f376
- https://sepolia.basescan.org/0x7e3abceb11f99e67d034154d125f80f4ecb2f376/0#code  

Contract "structs" address:  
0x101cc0b2d24b4b7dc08b0d1f2f98183677db65dc

Deployment and verification:
- https://sepolia.basescan.org/address/0x101cc0b2d24b4b7dc08b0d1f2f98183677db65dc
- https://sepolia.basescan.org/0x101cc0b2d24b4b7dc08b0d1f2f98183677db65dc/0#code  

Contract "errors" address:  
0x6b79056f627006b880ba0218c5d0596c208a3f51

Deployment and verification:
- https://sepolia.basescan.org/address/0x6b79056f627006b880ba0218c5d0596c208a3f51
- https://sepolia.basescan.org/0x6b79056f627006b880ba0218c5d0596c208a3f51/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
