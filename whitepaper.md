# AetherDAO lite-paper
The AetherDAO introduces 2 new Native Assets to the Cardano Ecosystem.
- originAether
- Aether

The AetherDAO offers individuals the ability to purchase Aether tokens via a bonding mechanism from the DAO, in addition to this, the DAO will purchase Aether tokens off of the market when the contents of the treasury sufficiently exceeds the current market cap of the token reflected in the integrated liquidity pool(s).

Any Aether owned by the DAO treasury will be used to stake into the yield bearing mechanism of the DAO until a point where the market cap sufficiently exceeds the treasury contents of the DAO. At this point the DAO will sell enough tokens to lower the market cap sufficiently OR expend all of the Aether held by the DAO. Additional liquidity in the DAOs treasury will be used to interact with defi protocols. When possible this will be done directly; where required, a native-script multi-sig will be leveraged.

In addition to the mechanisms above, the AetherDAO incentivizes holding Aether by offering a yield bearing mechanism known as staking. When you stake your Aether, you will earn an APY that is calculated based on:
1) The current treasury to market cap ratio.
2) The protocol parameters set in the governance module.
This is explained further below.

## Bonding
The bonding discount will be set by the DAO via standard proposals, these bonds take 1, 3, 12, or 18 epochs in order to mature, and the discounts are set differently for each according to risk profiles.

Bonding discounts will also vary depending on the collateral type used. All bonding discounts are set in the governance module via proposal.

By spending originAether upon bonding, a base discount of 10% is applied with up to an additional 40% in discount being applied on a sigmoid function that that reaches 95% of the additional discount being applied at the same rate of overcollateralization required for the DAO to purchase Aether.

The originAether tokens will be minted a single time with a total supply of 10 Million.
- 10% shall be allocated to the ADAOcommunity treasury.
- 10% shall be allocated for promotional purposes.
- 71.8% shall be allocated to the ADAO staking portal for holders of ADAO lp tokens to stake and earn originAether
- 8.2% shall be allocated to the team.

The originAether will be distributed over the course of 60 epochs:
- 200,000 per epoch for the first 12 epochs. - 2,400,000
- 160,000 per epoch for the next 12 epochs. - 1,920,000
- 120,000 per epoch for the next 12 epochs. - 1,420,000
- 80,000 per epoch for the next 12 epochs. - 960,000
- 40,000 per epoch for the next 12 epochs. - 480,000

## Staking
Staking payouts occur with a maximum frequency set in the governance module, for example 24 hours.
Some portion of rewards to be paid to the PAB operator will be set in the governance module, for example 5%.

This means that each account within the staking system may be updated once every 24 hours at most, 95% of rewards from the minting policy must be paid to the appropriate account(s), 5% of each accounts rewards may be collected by the bot that submits the transaction to mint these tokens.

A sigmoid function is used to determine the APY used, if the treasury is under-collateralizing the market cap of Aether, no rewards will be issued.

![alt text](https://github.com/AetherDAO-Repositories/AetherDAO-Documents/blob/main/images/i1.png)
Here the variable m is used to denote the maximum APR in terms of percentage, and this is likely to go to multiple decimal places.
The variable k is used to 'stretch out' the graph or increase the collateral ratio required to reach the maximum APR assigned by variable m.
![alt text](https://github.com/AetherDAO-Repositories/AetherDAO-Documents/blob/main/images/i2.png)

## DAO Stability: Purchase / Stake / Sell
A rate of collateralization will be set in the governance module for the purchasing and selling of Aether by the DAO.
For example, 120% over-collaterlization in order to execute purchase orders and 90% under-collateralization in order to execute sell orders.

This part is relatively straight forward, whenever the DAOs collateral ratio is above 120%, we will purchase Aether tokens off of the market and stake them. In addition the DAO will sell off its Aether tokens to the liquidity pool(s) integrated with the DAO assuming that the collateral ratio reaches 90%.

This results in the DAO always purchasing Aether tokens off of the market at a price that is condusive to the DAO continuing its operation.
Additionally bonding is limited to when the DAO is at a positive collateralization rate, further preventing dangerous capital expansion.

## DAO Stability: Purchase of LP Tokens
A rate of collateralization will be set in the governance module for the purchasing of Aether lp tokens by the DAO.
For example, 130% over-collaterlization in order to execute purchase orders.

This part is relatively straight forward, whenever the DAOs collateral ratio is above 130%, we will purchase Aether tokens off of the market and convert them into Aether lp tokens, this creates a sell pressure above this collateralization rate, but deepens the liquidity pool of the DAO.
These tokens are not sold by policy and are intended to increase deep liquidity. These tokens can be sold off by the DAO using a standard proposal under the Agora architecture.

## DAO Profit: DeFi
At the most basic level, the DAO will profit from having it's treasury contents staked to a pool that can be decided upon by the DAO. In addition to this, the DAO will seek to maximize yield and do so in a way that maximizes security of members - DeFi will be integrated directly where possible as opposed to leveraging multi-sigs.

Where necessary to interact with primitive DeFi the DAO will move funds into a multi-signature wallet that will be leveraged at the will of the DAO. This allows for the DAO to begin interacting with yield farming on Cardano at whatever point the AetherDAO protocol launches, instead of being limited to waiting for sufficiently advanced DeFi to be available.

The DAO will likely provide liquidity as well as lend through various platforms, in addition to leveraging tools such as undercollateralized flash-loans to arbitrage trade the market.

## DAO Profit: Smart Strategies and Yield Aggregators
By leveraging plutus validators, funds may be moved into contracts that enforce a specific yield farming strategy over a specified period of time before being redeemable by the DAO. By codifying specific strategies into validation logic, the DAO can trust that its liquidity is being deployed appropriately into the methods that will allow for the highest risk-adjusted returns to be achieved.
