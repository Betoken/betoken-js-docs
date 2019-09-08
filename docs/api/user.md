# betoken.user
Provides info of the manager account.

## `betoken.user.address()`
### Returns
`String`: the address of the user's Ethereum account.


## `betoken.user.sharesBalance()`
### Returns
`BigNumber`: the user's Betoken Shares balance.


## `betoken.user.sharesBalanceInDai()`
### Returns
`BigNumber`: the value of the user's Betoken Shares in Dai Stablecoin.


## `betoken.user.kairoBalance()`
### Returns
`BigNumber`: the user's Kairo balance, not including the Kairo used as stake.


## `betoken.user.tokenBalance(tokenSymbol)`
### Arguments
- `tokenSymbol: String`: the symbol of the token you want to query. ETH is also supported.

### Returns
`BigNumber`: the user's balance of the given token.


## `betoken.user.monthlyRoi()`
### Returns
`BigNumber`: the user's ROI for the current investment cycle, in percent. Takes into account the value of the active investments.


## `betoken.user.investmentList()`
### Returns
`Array<Object>`: list of the user's investments in the current investment cycle.

The investment objects have the following properties:

- `type: String`: type of the investment, one of `basic` `compound` and `fulcrum`.
- `id: Number`: ID of the investment. Investments of type `basic` and `fulcrum` share an ID system, `compound` investments has its own.
- `tokenSymbol: String`: symbol of the token that the investment invests in.
- `tokenAddress: String`: different for each type:
    - `basic`: address of the token
    - `fulcrum`: address of the Fulcrum position token
    - `compound`: address of the Compound cToken
- `stake: BigNumber`: amount of Kairo staked into the investment.
- `buyPrice: BigNumber`: different for each type:
    - `basic`: price of the token at time of investment
    - `fulcrum`: price of the Fulcrum position token at time of investment
    - `compound`: unavaiable
- `sellPrice: BigNumber`: different for each type:
    - `basic`: price of the token when the investment was sold, or the current price of the token if the investment is active.
    - `fulcrum`: price of the Fulcrum position token when the investment was sold, or the current price of the Fulcrum position token if the investment is active.
    - `compound`: unavailable
- `ROI: BigNumber`: the ROI of the investment when it was sold, or its current ROI if the investment is active, in percent.
- `kroChange: BigNumber`: the change of the Kairo staked in the investment since creation, equals `stake * (ROI / 100)`
- `currValue: BigNumber`: the current value of the Kairo staked in the investment, equals `stake + kroChange`
- `buyTime: Date`: the investment's time of creation.
- `isSold: Boolean`: whether or not the investment has been sold.

The following properties are exclusive to `fulcrum` and `compound` investments:

- `leverage: Number`: amount of leverage of the investment, always positive
- `orderType: Boolean`: `true` for short investments, `false` for long investments
- `safety: Boolean`: different for each type:
    - `fulcrum`: `false` if the position token's price is within 10% of the liquidation price, `true` otherwise
    - `compound`: `false` if the collateral ratio is within 10% of the liquidation threshold, `true` otherwise

The following properties are exclusive to `fulcrum` investments:

- `liquidationPrice: BigNumber`: the liquidation price of the Fulcrum position token. If the price is less than the liquidation price the position will be liquidated.

The following properties are exclusive to `compound` investments:

- `collateralRatio: BigNumber`: the current collateral ratio of the Compound investment.
- `currProfit: BigNumber`: the current profit of the Compound investment, in Dai Stablecoin.
- `currCollateral: BigNumber`: the current collateral of the Compound investment, in Dai Stablecoin.
- `currBorrow: BigNumber`: the current debt of the Compound investment, in Dai Stablecoin.
- `currCash: BigNumber`: the current cash held by the Compound investment, in Dai Stablecoin.
- `currLiquidity: BigNumber`: the current liquidity of the Compound investment, in Dai Stablecoin.
- `minCollateralRatio: BigNumber`: the minimum collateral ratio the Compound investment needs to maintain to avoid liquidation.
- `collateralAmountInDAI: BigNumber`: the initial collateral given to the Compound investment at time of creation, in Dai Stablecoin.


## `betoken.user.portfolioValue()`
### Returns
`BigNumber`: the user's Kairo balance, including the current value of the Kairo used as stake.


## `betoken.user.riskTakenPercentage()`
### Returns
`BigNumber`: the risk taken by the manager, expressed in percentage of the [Risk Threshold](https://betoken.gitbook.io/docs/manage-the-fund/how-does-risk-threshold-work).