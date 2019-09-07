# BetokenJS

Javascript API for managing the Betoken fund.

## Getting Started

### 1. Install via npm
```
npm install --save betoken-js
```

### 2. Import BetokenJS
```
const BetokenAPI = require('betoken-js');
```

### 3. Initialize BetokenJS with your web3 provider & Ethereum private key
```
const web3Provider = 'wss://mainnet.infura.io/ws/v3/...';
const privateKey = '0xdeadbeef';
const betoken = await BetokenAPI(web3Provider, privateKey);
```