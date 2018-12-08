# Cosmos Hub Testnet - *jenki-1000*

## The Steps

1. Install `v0.27.1` of the [cosmos-sdk](https://github.com/cosmos/cosmos-sdk)
2. Run `gaiad init --moniker=<moniker>`
3. Remove the existing genesis file with `rm $HOME/.gaiad/config/genesis.json`
4. Download the new [state.json](state.json) to `$HOME/.gaiad/config/genesis.json` with `wget -c 'https://raw.githubusercontent.com/cryptiumlabs/cosmos-testnets/master/jenki-1000/state.json' -O genesis.json`
5. (Optionally) Recover your GoS key with `gaiacli keys add <key-name> --recover`
6. Create a genesis transaction with
```bash
gaiad gentx \
  --amount 10000STEAK \
  --commission-rate "0.10" \
  --commission-max-rate "1.00" \
  --commission-max-change-rate "0.01" \
  --pubkey $(gaiad tendermint show-validator)  \
  --name <key-id>
```
7. Submit your genesis transaction as a github PR with a justification why you want to join and who you are. The file is in `$HOME/.gaiad/config/gentx`.
8. Remove the old genesis file with `rm $HOME/.gaiad/config/genesis.json`
9. Download the new [genesis.json](genesis.json) to `$HOME/.gaiad/config/genesis.json`
