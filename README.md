# Solidity Template

This template has been forked fom https://github.com/amanusk/hardhat-template (MIT license).

It includes an example of how to write an adapter for interacting with Ren's Gateway contracts, and a test file which sets up RenJS with the local contracts.

## Notes

If you are replicating this set-up in an existing repository, here's some things to note:

- Currently, the contracts in `@renproject/gateways-sol` need to be compiled with Solidity 0.5.17, do to some of its dependencies. Once these dependencies have been updated or replaced, `@renproject/gateways-sol` will also be updated. Hardhat has been configured to use two Solidity versions - "0.8.4" and "0.5.17".
- Due to these same dependencies, there are version clashes in the npm dependency tree which require some version overrides. If using `yarn`, add the following to `package.json`:

  ```json
  "resolutions": {
      "@resolver-engine/imports-fs": "^0.3.3",
      "@ethersproject/bignumber": "^5.3.0"
  },
  ```

---

---

**The rest of the README is part of the `amanusk/hardhat-template` template.**

## Usage

### Pre Requisites

Before running any command, make sure to install dependencies:

```sh
$ yarn install
```

### Compile

Compile the smart contracts with Hardhat:

```sh
$ yarn compile
```

### TypeChain

Compile the smart contracts and generate TypeChain artifacts:

```sh
$ yarn build
```

### Test

Run the Mocha tests:

```sh
$ yarn test
```

### Deploy contract to netowrk (requires Mnemonic and infura API key)

```
npx hardhat run --network rinkeby ./scripts/deploy.ts
```

### Validate a contract with etherscan (requires API ke)

```
npx hardhat verify --network <network> <DEPLOYED_CONTRACT_ADDRESS> "Constructor argument 1"
```
