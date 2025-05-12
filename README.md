# Foundry FundMe Project

Welcome to the **Foundry FundMe** project! This is a smart contract project built using Solidity and Foundry, designed to demonstrate a decentralized crowdfunding platform. The project includes a `FundMe` contract that allows users to fund the contract and withdraw funds, with price conversion powered by Chainlink.

---

## Features

- **Crowdfunding**: Users can send ETH to the contract to fund it.
- **Price Conversion**: Uses Chainlink's ETH/USD price feed to ensure a minimum funding amount in USD.
- **Owner-Only Withdrawals**: Only the contract owner can withdraw funds.
- **Fallback and Receive Functions**: Handles direct ETH transfers to the contract.

---

## Project Structure

### Contracts

1. **`FundMe.sol`**:
   - The main contract that handles funding and withdrawals.
   - Uses the `PriceConverter` library for ETH/USD conversion.
   - Includes a `MINIMUM_USD` constant to enforce a minimum funding amount.

2. **`PriceConverter.sol`**:
   - A library that interacts with Chainlink's price feed to fetch the latest ETH/USD price.
   - Provides a utility function to convert ETH to USD.

3. **`HelperConfig.s.sol`**:
   - A helper script to configure the network settings for deployment.
   - Includes configurations for Sepolia and Anvil networks.

4. **`DeployFundMe.s.sol`**:
   - A deployment script to deploy the `FundMe` contract on a blockchain.

### Tests

- **`FundMeTest.t.sol`**:
  - Unit tests for the `FundMe` contract.
  - Includes a test to verify the `MINIMUM_USD` constant.

---

## Prerequisites

To run this project, you need the following:

- [Foundry](https://book.getfoundry.sh/) installed on your system.
- A Sepolia RPC URL (e.g., from [Infura](https://infura.io/) or [Alchemy](https://www.alchemy.com/)).
- A basic understanding of Solidity and smart contract development.

---

## How to Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/GingerDaniel/FoundryFundMe.git

   cd foundry-fundme
   ```

2. **Install Dependencies**:
   ```bash
   forge install
   ```

3. **Configure Network Settings**:
   - Update the `HelperConfig.s.sol` file with your Sepolia RPC URL and private key.

4. **Deploy the Contract**:
   ```bash
   forge deploy --network sepolia
   ```

5. **Run Tests**:
   ```bash
   forge test
   ```

---

## How It Works

1. **Funding**:
   - Users call the `fund()` function to send ETH to the contract.
   - The contract checks if the sent ETH meets the minimum USD requirement using Chainlink's price feed.

2. **Withdrawals**:
   - Only the owner of the contract can call the `withdraw()` function to retrieve the funds.

3. **Price Conversion**:
   - The `PriceConverter` library fetches the latest ETH/USD price from Chainlink and converts ETH to USD.

---

## Technologies Used

- **Solidity**: Smart contract programming language.
- **Foundry**: A blazing-fast development framework for Ethereum.
- **Chainlink**: Decentralized oracle network for price feeds.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contributing

Contributions are welcome! Feel free to fork the repository and submit a pull request.

---

## Acknowledgements

- Inspired by the need for decentralized funding solutions.
- Leveraging Chainlink's reliable price feeds for accurate valuation.

---

## Author

Created by **Ginger Daniel**. Feel free to reach out for questions or collaboration opportunities!

