# betoken.tokens
Provides info of the tradable assets.

## `betoken.tokens.tokenData()`
### Returns
`Array<Object>`: list of information about supported assets.

Each object has the following properties:

- `name: String`: the name of the asset
- `symbol: String`: the symbol of the asset
- `address: String`: the address of the asset (0xeeeeee... for Ether)
- `decimals: Number`: the number of decimals used by the asset
- `price: BigNumber`: the current price of the asset, in Dai Stablecoin
- `dailyPriceChange: BigNumber`: the 24 hour change of the asset's price in Dai, in percent

## `betoken.tokens.assetSymbolToInfo(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`Object`: information about the asset. The properties are listed in [betoken.tokens.tokenData()](#betokentokenstokendata)

## `betoken.tokens.assetSymbolToPTokens(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`Array<Object>`: list of Fulcrum pTokens of the asset.

Each object has the following properties:

- `address: String`: address of the pToken
- `leverage: Number`: leverage of the pToken
- `type: Boolean`: `true` if it's a short pToken, `false` if it's a long pToken

## `betoken.tokens.assetSymbolToCTokenAddress(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`String`: the asset's corresponding Compound cToken's address.

## `betoken.tokens.assetAddressToSymbol(addr)`
### Arguments
- `addr: String`: the address of the asset you're querying.

### Returns
`String`: the symbol of the asset

## `betoken.tokens.assetPTokenAddressToInfo(addr)`
### Arguments
- `addr: String`: the address of the Fulcrum pToken you're querying.

### Returns

## `betoken.tokens.assetCTokenAddressToSymbol(addr)`
### Arguments
- `addr: String`: the address of the Compound cToken you're querying.

### Returns
`String`: the symbol of the cToken's underlying asset.

## `betoken.tokens.getPTokenPrice(addr, underlyingPrice)`
### Arguments
- `addr: String`: the address of the Fulcrum pToken you're querying.
- `underlyingPrice: BigNumber`: the current price of the pToken's underlying asset, in Dai Stablecoin.

### Returns
`BigNumber`: the current price of the pToken, in Dai Stablecoin.

## `betoken.tokens.notStablecoin(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`Boolean`: `true` if the asset is not a stablecoin (or something you won't want to invest in, such as WETH), `false` otherwise.

## `betoken.tokens.isCompoundToken(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`Boolean`: `true` if the asset supports Compound investments, `false` otherwise.

## `betoken.tokens.isFulcrumToken(symbol)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.

### Returns
`Boolean`: `true` if the asset supports Fulcrum investments, `false` otherwise.

## `betoken.tokens.fulcrumMinStake(symbol, isShort)`
### Arguments
- `symbol: String`: the symbol of the asset you're querying.
- `isShort: Boolean`: true for shorting, false for longing.

### Returns
`BigNumber`: the minimum Kairo needed to stake in a Fulcrum investment with the given parameters.