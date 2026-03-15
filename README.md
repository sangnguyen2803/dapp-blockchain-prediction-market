# dapp-blockchain-prediction-market

A decentralized prediction market platform built with Solidity smart contracts, Truffle, and a React frontend. Users can create markets, place bets, and resolve outcomes using an oracle.

---

## Project Structure

- **contracts/**: Solidity smart contracts (PredictionMarket, UMAOptimisticOracleMock)
- **client/**: React frontend (connects to deployed contracts)
- **migrations/**: Truffle migration scripts
- **build/**: Compiled contract artifacts
- **test/**: (Add your Truffle tests here)

---

## Prerequisites

- Node.js & npm
- Truffle (`npm install -g truffle`)
- Ganache (for local blockchain)
- MetaMask (browser extension)

---

## Setup Instructions

### 1. Clone the repository

```sh
git clone https://github.com/yourusername/dapp-blockchain-prediction-market.git
cd dapp-blockchain-prediction-market
```

### 2. Install dependencies

- **Root folder (for Truffle & contracts):**
    ```sh
    npm install
    ```

- **Client folder (for React frontend):**
    ```sh
    cd client
    npm install
    npm install web3 ethers react-router-dom
    ```

### 3. Compile and deploy contracts

- Start Ganache and ensure it runs on `localhost:7545` (network_id: 5777).
- In the root folder:
    ```sh
    truffle compile
    truffle migrate --reset --network development
    ```

### 4. Configure frontend

- Update the contract address in:
    - `client/src/utils/web3.js` (`deployedAddress`)
    - `client/src/components/market/OracleAdmin.js` (`CONTRACT_ADDRESS`, `ORACLE_PRIVATE_KEY`, `ADMIN_PASSWORD` as needed)

### 5. Run the frontend

- In the `client` folder:
    ```sh
    npm run deploy   # Copies contract ABIs to frontend
    npm start        # Starts React app at http://localhost:3000
    ```

---

## Usage

- **Create Market:** Users can create new prediction markets.
- **Place Bets:** Users bet on outcomes before the market end time.
- **Resolve Market:** Oracle admin resolves markets after they end (password-protected).
- **Claim Winnings:** Winners can claim their rewards after resolution.

---

## Smart Contracts

- **PredictionMarket.sol:** Main contract for market creation, betting, resolution, and claiming.
- **UMAOptimisticOracleMock.sol:** Mock oracle for simulating outcome proposals.

---

## Scripts

- `npm run deploy` (in client): Deploys contracts and copies ABIs to frontend.
- `npm start` (in client): Runs the React app.

---

## Notes

- Always update contract addresses in the frontend after redeploying contracts.
- Oracle admin credentials are hardcoded for demo; secure them for production.
- For testing, use the first Ganache account as the oracle.

---

