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

### Help

Use `yarn safe help <command>` to get more information about parameters of a command.

Example:
```bash
yarn safe help create
```

### Create Safe
Creates and setups a Safe proxy via the proxy factory. All parameters of the Safe `setup` method can be configured.

#### Example
This will deploy a Safe that uses the first imported account as an owner and set the threshold to 1.
```bash
yarn safe create
```

```bash
yarn safe create --factory 0xE89ce3bcD35bA068A9F9d906896D3d03Ad5C30EC --singleton 0xb4A7C7da1631CF60A2Cf23ABc86986f99a1A7f70 --fallback 0xe16bA5bF81E5BB113e4752E4fdC20351d796fB24 --signers 0x598FeaB9ff6A090a7fAA9dF0F3B4df3F0c8D35FC,0xc6AF1E96Cb0Fe864ccfC1d1Dcf4239A233A9B72a,0x4a79c58CCf9d80353c02357F26D6f7b99fA9991e  --threshold 2
```



### Safe Info
Displays information about a Safe

#### Usage
```bash
yarn safe info <address>
```

```bash
yarn safe info 0x276505D5a1231d0a6ec2fB8580ceaAB7f9B2647A      
```

### Propose Safe Transaction
Creates a proposal json file for a Safe transaction that can be shared. The name of the json file will be `<safe_tx_hash>.proposal.json` and it will be stored in the `cli_cache` folder.

#### Examples
This will create a transaction from the Safe to the target without any value or data.
```bash
yarn safe propose <address> --to <target>
```

This will create a transaction based on the sample tx input json that mints some WETH and sets an approve for it.
```bash
yarn safe propose-multi <address> tx_input.sample.json
```

```bash
yarn safe propose-multi 0x276505D5a1231d0a6ec2fB8580ceaAB7f9B2647A tx_input.approve.json
```


### Show Proposal
Shows the information of the proposal. 
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe show-proposal <safeTxHash>
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
### Submit Proposal
Submits a proposal with the imported account
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe submit-proposal <safeTxHash>
```
```bash
yarn safe submit-proposal 0x8ea6536180b1827226957ca1492f3dbd96c278665d4321bb5aa7740bdd7d2e72
```
### Show Transaction History
Displays the transaction history of a Safe based on events

#### Usage
```bash
yarn safe history <address>
```
```bash
yarn safe history 0xc2d76d0b31A7FfD239Bf7d75bF4fB2B5307361d4
```


Security and Liability
----------------------
All contracts are WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

License
-------
All smart contracts are released under LGPL-3.0
