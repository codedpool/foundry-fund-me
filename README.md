🦊 **Foundry Fund Me** 🦊

Welcome to the **Foundry Fund Me** project! This guide will help you get started quickly and efficiently. Let’s dive in! 🚀

## Table of Contents

- Getting Started
  - Requirements
  - Quickstart
- Usage
  - Deploy
  - Testing
    - Test Coverage
  - Local zkSync
    - Requirements
    - Setup Local zkSync Node
    - Deploy to Local zkSync Node
- Deployment to a Testnet or Mainnet
  - Scripts
    - Withdraw
  - Estimate Gas
- Formatting
- Additional Info
  - About "Official"
  - Summary
- Thank You!

---

## Getting Started

### Requirements

- **Git**: Install it [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). Verify with:
  `git --version`
- **Foundry**: Install it [here](https://getfoundry.sh/). Verify with:
  `forge --version`

### Quickstart

Navigate to the project directory and run the following command:
`cd foundry-fund-me`
`make`

---

## Usage

### Deploy

To deploy the contract:
`forge script script/DeployFundMe.s.sol`

### Testing

Run tests using:
`forge test`

Target specific tests:
`forge test --match-test testFunctionName`

For forked testing:
`forge test --fork-url $SEPOLIA_RPC_URL`

#### Test Coverage

To check the test coverage:
`forge coverage`

---

## Local zkSync

### Requirements

- **Foundry zkSync**: Install from [foundry-zksync](https://github.com/matter-labs/foundry-zksync). Verify with:
  `forge --version`
- **npm & npx**: Verify installations with:
  `npm --version` and `npx --version`

### Setup Local zkSync Node

1. Configure the node:
   `npx zksync-cli dev config`
   Select "In memory node" and skip additional modules.
2. Start the node:
   `npx zksync-cli dev start`

### Deploy to Local zkSync Node

Deploy contracts to the local zkSync node:
`make deploy-zk`

---

## Deployment to a Testnet or Mainnet

1. **Setup Environment Variables**  
   Add the following to a `.env` file:

   - `PRIVATE_KEY`: Your account's private key (use one with no real funds).
   - `SEPOLIA_RPC_URL`: Your testnet RPC URL from [Alchemy](https://alchemy.com).
   - Optionally, add `ETHERSCAN_API_KEY` for contract verification.

2. **Get Testnet ETH**  
   Obtain testnet ETH from [faucets.chain.link](https://faucets.chain.link/).

3. **Deploy**  
   Run the following command:
   `forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY`

---

### Scripts

Interact with deployed contracts:
`cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>`

#### Withdraw

Withdraw funds using:
`cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()" --private-key <PRIVATE_KEY>`

---

## Estimate Gas

Generate a gas report with:
`forge snapshot`

---

## Formatting

Format your code:
`forge fmt`

---

## Additional Info

### About "Official"

The `chainlink-brownie-contracts` repository is an official Chainlink resource. It is maintained by Chainlink's team and integrates with their release cycle.

### Summary

1. **Official Repo**: Maintained by Chainlink.
2. **Integration**: Uses npm releases for seamless Foundry usage.

---

## Thank You!

Thank you for exploring the **Foundry Fund Me** project! Your support means a lot. Happy coding! 🦊

**Romanch Roshan Singh** 🦊
