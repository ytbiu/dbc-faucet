## Faucet for dbc testnet chain

This repo is a fork of https://github.com/paritytech/polkadot-testnet-faucet, yet it is now its
own being:

- it has the same codebase as the upstream repo when it comes to basic functionality (sending tokens),
  although that codebase is pretty old (from 2019)
- it does not have matrix functionality
- it has AlephZero own branding
- It is used only on Devnet and Tesnet environments.

## Development

Setup dependencies and git hooks

```bash
yarn install
yarn simple-git-hooks
```

To launch a hot-reloading dev environment

```bash
yarn dev:backend
```

To launch faucet frontend

```bash
yarn page
```

and then open [http://localhost:5556](http://localhost:5556) in your web browser.

## Docker development

```bash
docker build --tag faucet:latest -f Dockerfile .
docker run --rm -it --network=host --name faucet faucet:latest dev:backend
docker run --rm -it --network=host --name faucet-frontend faucet:latest page
```

## Server environment variables

Setup a .env file with the following variables, example

```bash
FAUCET_ACCOUNT_MNEMONIC="this is a fake mnemonic"
NETWORK_DECIMALS=15
PORT=5555
RPC_ENDPOINT="http://localhost:9944"
NETWORK_UNIT="DBC"
COOLDOWN=100
BACKEND_URL=http://localhost:5555
DRIP_AMOUNT=150
ENV=Testnet
```
