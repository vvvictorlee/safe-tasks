Gnosis Safe Tasks
=================

Install
-------
Set correct node version (see `.nvmrc`) with [nvm](https://github.com/nvm-sh/nvm)
```bash
nvm use
```

Install requirements with yarn:
```bash
yarn
```

Quick Start
-----------
### Setup

Create `.env` file to use the commands (see `.env.sample` for more info):

- `NETWORK` - Network that should be used (e.g. `rinkeby`, `mainnet` or `custom`)
- `PK` or `MNEMONIC`- Credentials for the account that should be used
- `INFURA`- For network that use Infura based RPC
- `NODE`- RPC node for `custom` network (optional)


### Show Proposal
Shows the information of the proposal. 
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe show-proposal <safeTxHash> <safeAddress>
```

```bash
yarn safe show-proposal 0x8ea6536180b1827226957ca1492f3dbd96c278665d4321bb5aa7740bdd7d2e72 0x276505D5a1231d0a6ec2fB8580ceaAB7f9B2647A
```


### Sign Proposal
Signs a proposal with the imported account
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe sign-proposal <safeTxHash>
```

```bash
yarn safe sign-proposal 0x8ea6536180b1827226957ca1492f3dbd96c278665d4321bb5aa7740bdd7d2e72
```

