# BetokenJS

Javascript API for managing the Betoken fund. Start building trading bots & apps on top of Betoken crowd-powered crypto-assets management protocol.

## What is Betoken JS?
Betoken JS is a multipurpose API allowing fund managers, investors, and DeFi users to create and automate new ways to interact with Betoken fund.

### Fund Managers
It will serve as a base platform upon which fund managers with limited technical expertise can plug their crypto trading bots, set up their limit orders or build new applications to interact directly with Betoken ecosystem.

### Investors
Investors will be able to automate the monitoring of their Betoken shares and set up automated deposits and withdrawals.

### DeFi buiDlers
Developers of DeFi apps with the goal to unify the DeFi landscape can allow their users to interact with Betoken ecosystem without living their UI.

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
[BetokenJS documentation](https://betoken.fund/betoken-js-docs/)
