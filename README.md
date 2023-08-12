## Stablecoin pegged to USD

DSC (decentralized stablecoin) is backed by deposited wETH, wBTC. Value of collateral checked with Chainlink Price Feed.

DSCEngine.sol is the deposit contract to redeem Ethereum and bitcoin for DSC, and minting DSC after inputting collateral.

Min collaterization: $2 in collateral for every $1 DSC loaned

When an user is undercollateralized, a liquidator has the option to pay back X DSC to recieve $(1.1 X) worth of the debtor's collateral.  

Follows Patrick Collin's Cyfrin 2023 course on Stablecoin.

**Stability mechanism (minting): algorithmic** <br> 
No controlling entity

**Collateral: Exogenous (crypto)**<br> 
Ethereum and Bitcoin collateralizes this stablecoin. Specifically wETH, wBTC.

### Roadmap

A collateral backed by Treasury bills and LSDs. 
    - Value of collateral assets confirmed by Chainlink Oracles.

### Test coverage

| File                            | % Lines         | % Statements    | % Branches     | % Funcs        |
|---------------------------------|-----------------|-----------------|----------------|----------------|
| script/DeployDSC.s.sol          | 0.00% (0/11)    | 0.00% (0/14)    | 100.00% (0/0)  | 0.00% (0/1)    |
| script/HelperConfig.s.sol       | 0.00% (0/10)    | 0.00% (0/15)    | 0.00% (0/2)    | 0.00% (0/2)    |
| src/DSCEngine.sol               | 82.35% (56/68)  | 86.52% (77/89)  | 62.50% (10/16) | 66.67% (14/21) |
| src/DecentralizedStableCoin.sol | 66.67% (8/12)   | 71.43% (10/14)  | 50.00% (4/8)   | 100.00% (2/2)  |
| test/fuzz/Handler.t.sol         | 0.00% (0/28)    | 0.00% (0/35)    | 0.00% (0/10)   | 0.00% (0/4)    |
| test/fuzz/InvariantsTest.t.sol  | 0.00% (0/13)    | 0.00% (0/18)    | 0.00% (0/2)    | 0.00% (0/3)    |
| test/mocks/MockMoreDebtDSC.sol  | 0.00% (0/13)    | 0.00% (0/15)    | 0.00% (0/8)    | 0.00% (0/2)    |
| test/mocks/MockV3Aggregator.sol | 46.67% (7/15)   | 46.67% (7/15)   | 100.00% (0/0)  | 40.00% (2/5)   |
| Total                           | 41.76% (71/170) | 43.72% (94/215) | 30.43% (14/46) | 45.00% (18/40) |

