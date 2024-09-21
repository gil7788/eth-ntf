## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```

## Used Commands
### Installed Dependencies
forge install transmissions11/solmate

**ENV VARS**
```shell
$RPC_URL $CONTRACT_ADDRESS = http://127.0.0.1:8545 (Anvil - localnet)
$CONTRACT = deployed contract address
$OWNER = deployer
$PRIVATE_KEY = owner private key
```

To create the contract:
```shell
forge create NFT --rpc-url=$RPC_URL --private-key=$PRIVATE_KEY --constructor-args "MyNFT" "MNFT"
```
### Anvil - Localnet
**Contract address**
0x5fbdb2315678afecb367f032d93f642f64180aa3
**Deployer (OWNER)**
0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266


**To Mint NTF using already deployed contract:**
```shell
cast send --rpc-url=$RPC_URL $CONTRACT_ADDRESS  "mintTo(address)" --private-key=$PRIVATE_KEY
```

```shell
cast call --rpc-url=$RPC_URL --private-key=$PRIVATE_KEY $CONTRACT_ADDRESS "ownerOf(uint256)" 1
```

