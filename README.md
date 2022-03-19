# ff-near-contracts

This repository contains few and far smart contracts.

## Marketplace contract

Testnet contract address: market.fewandfar.testnet

## How to deploy
Use the following commands to deploy the contract:

```bash
export NEAR_ENV=testnet
near create-account market.fewandfar.testnet --masterAccount fewandfar.testnet --initialBalance 5
near deploy --account_id market.fewandfar.testnet --wasmFile out/FewAndFar.wasm
```

## Commands
Please refer to contracts/marketplace/README.md