# betoken.investorActions
Allows the user to deposit/withdraw their money in the Betoken fund.

## `betoken.investorActions.depositETH(amt, onPending, onConfirm, onError)`
Allows an investor to deposit into the fund using Ether.

### Arguments
- `amt: BigNumber | String | Number`: the amount of Ether to deposit
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.investorActions.depositDAI(amt, onPending, onConfirm, onError)`
Allows an investor to deposit into the fund using Dai Stablecoin.

### Arguments
- `amt: BigNumber | String | Number`: the amount of DAI to deposit
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.

## `betoken.investorActions.depositToken(amt, tokenSymbol, onPending, onConfirm, onError)`
Allows an investor to deposit into the fund using an ERC20 token supported by Kyber Network, other than Dai Stablecoin.

### Arguments
- `amt: BigNumber | String | Number`: the amount of token to deposit
- `tokenSymbol: String`: the symbol of the token used for deposit
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.investorActions.withdrawETH(amt, onPending, onConfirm, onError)`
Allows an investor to withdraw their money from the fund in Ether.

### Arguments
- `amt: BigNumber | String | Number`: the amount to withdraw, in Dai Stablecoin
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.investorActions.withdrawDAI(amt, onPending, onConfirm, onError)`
Allows an investor to withdraw their money from the fund in Dai Stablecoin.

### Arguments
- `amt: BigNumber | String | Number`: the amount to withdraw, in Dai Stablecoin
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.investorActions.withdrawToken(amt, tokenSymbol, onPending, onConfirm, onError)`
Allows an investor to withdraw their money from the fund in an ERC20 token supported by Kyber Network, other than Dai Stablecoin.

### Arguments
- `amt: BigNumber | String | Number`: the amount to withdraw, in Dai Stablecoin
- `tokenSymbol: String`: the symbol of the token to used for the withdrawal
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.


## `betoken.investorActions.nextPhase(onPending, onConfirm, onError)`
Transitions the Betoken fund to the next investment phase. This affects all Betoken users, and the manager that calls this function first is rewarded 1 KRO.
### Arguments
- `onPending: (txHash) =>`: callback for when the transaction hash is available
- `onConfirm: (receipt) =>`: callback for when the transaction has been accepted into an Ethereum block
- `onError: (error) =>`: callback for when there's an error

### Returns
`Promise`: resolves when the transaction has been sent.