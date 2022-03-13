# Few and Far marketplace

To deploy the smart contract create a dedicated account:

```bash
near create-account market.fewandfar.testnet --masterAccount fewandfar.testnet --initialBalance 25
near deploy --wasmFile out/market_new.wasm --accountId market.fewandfar.testnet
```

# Initialize
near call market.fewandfar.testnet new '{"owner_id": "fewandfar.testnet", "ft_token_ids":[], "use_storage_fees": true}' --accountId market.fewandfar.testnet

# Deposits
In order to publish a sale users have to deposit tokens to the contract. Each sale use 0.1 NEAR. NEAR are locked into the contract until sale end, then user can withdraw them using the withdrawal function:

```bash
near call market.fewandfar.testnet storage_deposit --accountId fewandfar.testnet --deposit 1 
```

# Publish NFS


near call paras-token-v2.testnet nft_approve '{"token_id": "210:18","account_id": "market.fewandfar.testnet","msg": "{\"sale_conditions\": {\"near\": \"1\"}}"}'  --account-id fewandfar.testnet --deposit 1 --gas 300000000000000

# get sales
near view market.fewandfar.testnet get_supply_sales
near view market.fewandfar.testnet get_sales '{"from_index": "0", "limit": 10}'
