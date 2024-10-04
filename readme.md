# EVM Subnet DeFi Game Contracts - README

This repository contains two smart contracts: `ERC20` and `Vault`. These contracts are essential for the DeFi game environment, which involves token minting, transfers, and staking mechanisms. This guide will explain the steps to set up and deploy the contracts using **Remix IDE** with **Metamask** as the injected provider.

## Table of Contents
1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [Setting Up an EVM Subnet](#setting-up-an-evm-subnet)
4. [Metamask Configuration](#metamask-configuration)
5. [Contracts](#contracts)
    - [ERC20 Contract](#erc20-contract)
    - [Vault Contract](#vault-contract)
6. [Deploying the Contracts using Remix](#deploying-the-contracts-using-remix)
7. [License](#license)

## Overview

This repository provides Solidity contracts for a DeFi game environment. The contracts include:
- **ERC20** contract for minting, transferring, and burning an in-game currency.
- **Vault** contract for token deposits and withdrawals (staking mechanism).

These contracts are deployed on an **Avalanche EVM subnet** and are configured to interact with **Metamask**.

## Prerequisites

Before getting started, ensure you have:
- **Remix IDE**: You can access Remix IDE from your browser at [Remix](https://remix.ethereum.org/).
- **Metamask**: Installed and set up with the EVM Subnet.
- **Avalanche EVM Subnet**: A custom EVM subnet for deployment.
- **Solidity Version**: ^0.8.17 (used in the contracts).

## Setting Up an EVM Subnet

1. **Create a Custom EVM Subnet:**
   Follow the [Avalanche Documentation](https://docs.avax.network/) to create an EVM-based subnet. This subnet will be the foundation for your in-game economy and contracts.

2. **Define Your Native Currency:**
   Set up your custom native currency that will be used for transactions in your game (using the `ERC20` contract for token management).

## Metamask Configuration

1. **Add Your Custom EVM Subnet to Metamask:**
   - Open Metamask and navigate to **Settings > Networks**.
   - Click **Add Network** and fill in the details of your subnet:
     - Network Name: `DeFi Game Subnet`
     - RPC URL: `<your-subnet-rpc-url>`
     - Chain ID: `<your-subnet-chain-id>`
     - Symbol: `<native-token-symbol>`
   - Save and connect your wallet to the newly added subnet.

2. **Adding Custom Tokens:**
   After deploying the `ERC20` contract, add the token to Metamask by providing the contract address and symbol (e.g., `SOLBYEX`).

## Contracts

### 1. ERC20 Contract

The `ERC20` contract is a custom token contract that supports minting, transferring, and burning tokens. It follows the ERC-20 standard.

#### Key Functions:
- `transfer(address recipient, uint amount)`: Transfer tokens to a recipient.
- `approve(address spender, uint amount)`: Approve a spender to transfer a certain number of tokens on behalf of the owner.
- `transferFrom(address sender, address recipient, uint amount)`: Transfers tokens from a sender to a recipient, typically used after approval.
- `mint(uint amount)`: Mints new tokens and increases total supply.
- `burn(uint amount)`: Burns tokens, reducing total supply.

### 2. Vault Contract

The `Vault` contract allows users to stake tokens by depositing them and receiving shares in return. The shares can later be burned to withdraw the corresponding tokens.

#### Key Functions:
- `deposit(uint amount)`: Deposits tokens into the vault, minting shares proportional to the total supply.
- `withdraw(uint shares)`: Burns shares and withdraws the underlying tokens.

## Deploying the Contracts using Remix

To deploy the contracts using **Remix IDE** and **Metamask**, follow these steps:

1. **Open Remix IDE:**
   - Go to [Remix IDE](https://remix.ethereum.org/).
   - Create a new file and paste the `ERC20` and `Vault` contract code into separate files.

2. **Connect Metamask:**
   - On the left side panel in Remix, go to the **Deploy & Run Transactions** tab.
   - Under **Environment**, select **Injected Web3**. This will connect Remix to the Metamask wallet.
   - Ensure your Metamask wallet is connected to your custom EVM subnet.

3. **Compile the Contracts:**
   - In the left-side panel, go to the **Solidity Compiler** tab.
   - Choose the Solidity version ^0.8.17 and click **Compile** for both the `ERC20` and `Vault` contracts.

4. **Deploy the Contracts:**
   - After compiling, go back to the **Deploy & Run Transactions** tab.
   - Select the `ERC20` contract from the dropdown and click **Deploy**.
   - Confirm the transaction in Metamask.
   - Repeat the process to deploy the `Vault` contract. Provide the `ERC20` token's address as the constructor parameter when deploying the `Vault` contract.

5. **Interact with the Contracts:**
   - After deployment, you will see the contracts in the **Deployed Contracts** section of Remix.
   - You can now interact with the contracts (mint tokens, transfer tokens, deposit to the vault, etc.) through the UI, or use Metamask to monitor the transactions.

## Author
Satyam Jha (satyammjha0@gmail.com)

## License

This repository is licensed under the MIT License. You are free to use, modify, and distribute the code as long as you retain the license information.
