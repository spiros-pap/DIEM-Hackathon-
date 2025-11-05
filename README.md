# Album Dashboard - Blockchain Demo

This is a decentralized application (dApp) for managing music album information on the Ethereum blockchain.

## Components

1. **Album-final.sol** - Solidity smart contract for storing album data
2. **index.html** - Web interface to interact with the contract
3. **main.css** - Styling for the interface

## Prerequisites

To run this application, you need:

1. **Ganache** - Local Ethereum blockchain
   - Download from: https://trufflesuite.com/ganache/
   - Start Ganache and note the RPC Server address (default: ws://localhost:7545)

2. **Web3.js** - Already installed via npm

3. **MetaMask** (optional) - Browser extension for Ethereum wallet

## Setup Instructions

### Step 1: Deploy the Smart Contract

1. Open Ganache and start a workspace
2. Use Remix IDE (https://remix.ethereum.org/) or Truffle to deploy `Album-final.sol`
3. Note down:
   - Your account address (from Ganache)
   - The deployed contract address
   - The contract ABI (from compilation)

### Step 2: Configure the HTML File

In `index.html`, update these variables (around line 52-53):

```javascript
var myAccountNumber = 'YOUR_GANACHE_ACCOUNT_ADDRESS';
var myContractAddress = 'YOUR_DEPLOYED_CONTRACT_ADDRESS';
```

And on line 63, paste the contract ABI:

```javascript
var albumContract = new web3.eth.Contract([YOUR_CONTRACT_ABI]);
```

### Step 3: Run the Application

Simply open `index.html` in a web browser, or use a local server:

```bash
# Using Python (if installed)
python -m http.server 8000

# Using Node.js http-server (install first: npm install -g http-server)
http-server
```

Then navigate to: http://localhost:8000

## Features

- **View Current Album**: See the album information set by the contract owner
- **Update Current Album**: (Owner only) Change the shared album information
- **Set Personal Favorite**: Each user can set their own favorite album
- **Real-time Events**: Get notifications when albums are updated

## Configuration Status

⚠️ **Before running, you must:**
- [ ] Deploy the smart contract to Ganache
- [ ] Update `myAccountNumber` in index.html
- [ ] Update `myContractAddress` in index.html
- [ ] Update the contract ABI in index.html

## Notes

- The contract owner (deployer) is the only one who can update the "current album"
- All users can set their own personal favorite album
- Make sure Ganache is running on ws://localhost:7545
