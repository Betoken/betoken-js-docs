# betoken.managerActions
Allows the user to create investments and margin orders, sell them, and maintain the collateration of margin orders.

## `betoken.managerActions.newInvestmentWithSymbol(tokenSymbol, stakeInKRO, minPrice, maxPrice, onPending, onConfirm, onError)`
Creates a new investment into an asset specified by its symbol.

### Available during investment phase
Manage

### Arguments
- `tokenSymbol: String`: the asset's symbol
- `stakeInKRO: BigNumber`: the amount of Kairo to stake into the investment
- `minPrice: BigNumber`: the minimum acceptable price for the asset
- `maxPrice: BigNumber`: the maximum acceptable price for the asset
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.newInvestmentWithSymbol(tokenAddress, stakeInKRO, minPrice, maxPrice, onPending, onConfirm, onError)`
Creates a new investment into an asset/Fulcrum pToken specified by its address.

### Available during investment phase
Manage

### Arguments
- `tokenAddress: String`: the asset/pToken's address
- `stakeInKRO: BigNumber`: the amount of Kairo to stake into the investment
- `minPrice: BigNumber`: the minimum acceptable price for the asset/pToken
- `maxPrice: BigNumber`: the maximum acceptable price for the asset/pToken
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.sellInvestment(id, sellProportion, minPrice, maxPrice, onPending, onConfirm, onError)`
Sells a basic/Fulcrum investment.

### Available during investment phase
Manage

### Arguments
- `id: Number`: the ID of the investment
- `sellProportion: Number`: the proportion of the investment to sell, between 0 and 1
- `minPrice: BigNumber`: the minimum acceptable price for the asset/pToken
- `maxPrice: BigNumber`: the maximum acceptable price for the asset/pToken
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.newCompoundOrder(orderType, tokenSymbol, stakeInKRO, minPrice, maxPrice, onPending, onConfirm, onError)`
Creates a Compound margin order of the given asset.

### Available during investment phase
Manage

### Arguments
- `orderType: Boolean`: `true` for shorting, `false` for longing
- `tokenSymbol: String`: the asset's symbol
- `stakeInKRO: BigNumber`: the amount of Kairo to stake into the investment
- `minPrice: BigNumber`: the minimum acceptable price for the asset
- `maxPrice: BigNumber`: the maximum acceptable price for the asset
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.sellCompoundOrder(id, minPrice, maxPrice, onPending, onConfirm, onError)`
Sells a Compound margin order.

### Available during investment phase
Manage

### Arguments
- `id: Number`: the ID of the Compound order to sell
- `minPrice: BigNumber`: the minimum acceptable price for the asset
- `maxPrice: BigNumber`: the maximum acceptable price for the asset
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.repayCompoundOrder(id, amountInDAI, onPending, onConfirm, onError)`
Repays the debt of a Compound margin order using its cash.

### Available during investment phase
Manage

### Arguments
- `id: Number`: the ID of the Compound order to repay
- `amountInDAI: BigNumber`: the amount of debt to repay, in DAI
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.redeemCommission(inShares, onPending, onConfirm, onError)`
Redeems the total commission balance for the manager.

### Available during investment phase
Intermission

### Arguments
- `inShares: Boolean`: `true` to redeem commission in Betoken Shares, `false` to redeem in DAI
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.redeemCommissionForCycle(inShares, cycle, stakeInKRO, minPrice, maxPrice, onPending, onConfirm, onError)`
Redeems the commission of a particular cycle for the manager. Only use if `redeemCommission()` fails.

### Available during investment phase
Intermission

### Arguments
- `inShares: Boolean`: `true` to redeem commission in Betoken Shares, `false` to redeem in DAI
- `cycle: Number`: the investment cycle
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.nextPhase(onPending, onConfirm, onError)`
Transitions the Betoken fund to the next investment phase when the current phase is over. This affects all Betoken users, and the manager that calls this function first is rewarded 1 KRO.

### Available during investment phase
All

### Arguments
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.registerWithDAI(amountInDAI, onPending, onConfirm, onError)`
Registers the user as a Betoken fund manager, using DAI to pay for the cost. Can only be called once per user.

### Available during investment phase
All

### Arguments
- `amountInDAI: BigNumber`: the amount to pay, in DAI
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.registerWithETH(amountInETH, onPending, onConfirm, onError)`
Registers the user as a Betoken fund manager, using Ether to pay for the cost. Can only be called once per user.

### Available during investment phase
All

### Arguments
- `amountInETH: BigNumber`: the amount to pay, in Ether
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.managerActions.registerWithToken(amountInToken, tokenSymbol, onPending, onConfirm, onError)`
Registers the user as a Betoken fund manager, using an ERC20 token supported by Kyber Network to pay for the cost. Can only be called once per user.

### Available during investment phase
All

### Arguments
- `amountInToken: BigNumber`: the amount to pay, in the specified token
- `tokenSymbol: String`: the symbol of the token used for payment
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.