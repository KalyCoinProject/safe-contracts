Gnosis Safe Contracts for KalyChain
=====================

[![npm version](https://badge.fury.io/js/%40gnosis.pm%2Fsafe-contracts.svg)](https://badge.fury.io/js/%40gnosis.pm%2Fsafe-contracts)
[![Build Status](https://github.com/gnosis/safe-contracts/workflows/safe-contracts/badge.svg?branch=development)](https://github.com/gnosis/safe-contracts/actions)
[![Coverage Status](https://coveralls.io/repos/github/gnosis/safe-contracts/badge.svg?branch=development)](https://coveralls.io/github/gnosis/safe-contracts)

Usage
-----
### Install requirements with yarn:

```bash
yarn
```

### Run all tests:

```bash
yarn build
yarn test
```

### Deployments

### KalyChain Testnet

- Create2 Deployer: [0x4e59b44847b379578588920ca78fbf26c0b4956c](https://testnet.kalyscan.io/address/0x4e59b44847b379578588920ca78fbf26c0b4956c)

- SimulateTxAccessor: [0x59AD6735bCd8152B84860Cb256dD9e96b85F69Da](https://testnet.kalyscan.io/address/0x59AD6735bCd8152B84860Cb256dD9e96b85F69Da)

- GnosisSafeProxyFactory: [0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2](https://testnet.kalyscan.io/address/0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2) 

- DefaultCallbackHandler: [0x1AC114C2099aFAf5261731655Dc6c306bFcd4Dbd](https://testnet.kalyscan.io/address/0x1AC114C2099aFAf5261731655Dc6c306bFcd4Dbd)

- CompatibilityFallbackHandler: [0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4](https://testnet.kalyscan.io/address/0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4) 

- CreateCall: [0x7cbB62EaA69F79e6873cD1ecB2392971036cFAa4](https://testnet.kalyscan.io/address/0x7cbB62EaA69F79e6873cD1ecB2392971036cFAa4)

- MultiSend: [0xA238CBeb142c10Ef7Ad8442C6D1f9E89e07e7761](https://testnet.kalyscan.io/address/0xA238CBeb142c10Ef7Ad8442C6D1f9E89e07e7761)

- MultiSendCallOnly: [0x40A2aCCbd92BCA938b02010E17A5b8929b49130D](https://testnet.kalyscan.io/address/0x40A2aCCbd92BCA938b02010E17A5b8929b49130D)

- GnosisSafeL2: [0x3E5c63644E683549055b9Be8653de26E0B4CD36E](https://testnet.kalyscan.io/address/0x3E5c63644E683549055b9Be8653de26E0B4CD36E)

- GnosisSafe: [0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552](https://testnet.kalyscan.io/address/0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552)

### Deploy

> :warning: **Make sure to use the correct commit when deploying the contracts.** Any change (even comments) within the contract files will result in different addresses. The tagged versions that are used by the Gnosis Safe team can be found in the [releases](https://github.com/gnosis/safe-contracts/releases).

This will deploy the contracts deterministically and verify the contracts on etherscan using [Solidity 0.7.6](https://github.com/ethereum/solidity/releases/tag/v0.7.6) by default.

Forked from [Safe Contracts v1.3.0](https://github.com/safe-global/safe-contracts/releases/tag/v1.3.0)

Preparation:
- Set `NODE_URL` in `.env`
- Set `PK` in `.env`


```bash
yarn deploy-all custom
```

This will perform the following steps

```bash
yarn build
yarn hardhat --network custom deploy
yarn hardhat --network custom etherscan-verify
yarn hardhat --network custom local-verify
```

#### Custom Networks

It is possible to use the `NODE_URL` env var to connect to any EVM based network via an RPC endpoint. This connection then can be used with the `custom` network.

E.g. to deploy the Safe contract suite on that network you would run `yarn deploy-all custom`. 

The resulting addresses should be on all networks the same.

Note: Address will vary if contract code is changed or a different Solidity version is used.

### Verify contract

This command will use the deployment artifacts to compile the contracts and compare them to the onchain code
```bash
yarn hardhat --network custom local-verify
```

This command will upload the contract source to Etherescan
```bash
yarn hardhat --network custom etherscan-verify
```

### Known issue

Contract verification fails due to KalyScan not included in @nomiclabs/hardhat-etherscan

Documentation
-------------
- [Safe developer portal](http://docs.gnosis.io/safe)
- [Error codes](docs/error_codes.md)
- [Coding guidelines](docs/guidelines.md)

Audits/ Formal Verification
---------
- [for Version 1.3.0 by G0 Group](docs/audit_1_3_0.md)
- [for Version 1.2.0 by G0 Group](docs/audit_1_2_0.md)
- [for Version 1.1.1 by G0 Group](docs/audit_1_1_1.md)
- [for Version 1.0.0 by Runtime Verification](docs/rv_1_0_0.md)
- [for Version 0.0.1 by Alexey Akhunov](docs/alexey_audit.md)

Security and Liability
----------------------
All contracts are WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

License
-------
All smart contracts are released under LGPL-3.0


