# Cosmos Hub Testnet - *jenki-1000*

## Submit a genesis transaction

We are trying to start a testnet from the Cosmos Validator Community to test the bug fixes and practice the start of Game of Stakes.

To be bonded at genesis, you need to generate a genesis transaction and submit it.

### To generate a genesis transaction,

install `v0.27.1` of the Cosmos SDK.

run `gaiad init`

Download [genesis](genesis.json) to `$HOME/.gaiad/config/genesis.json`

if you need to recover the key you used for signup do

`gaiacli keys add <key-id>  --recover`


```
gaiad gentx \
  --amount 10000STAKE \
  --commission-rate "0.10" \
  --commission-max-rate "1.00" \
  --commission-max-change-rate "0.01" \
  --pubkey $(gaiad tendermint show-validator)  \
  --name <key-id>
```

This will generate a file roughly like `$HOME/.gaiad/config/gentx/gentx-c00ce0b868bd5d5576d23f0ad1090f3f478b7961.json`
