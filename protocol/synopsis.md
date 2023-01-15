# Overview

## Protocol Participants

In Mirror Protocol, users act in one or more of the following roles:

* Trader
* Minter & Shorter
* Liquidity Provider
* Staker

In addition, there are special auxiliary agents that are required for Mirror's infrastructure:

* Oracle Feeder

### Trader

A **trader** engages in buying and selling mAssets against ETH through [Ethereumswap](ethereumswap.md) and benefits from price exposure via mAssets.

### Minter & Shorter 

A **minter** is a user that enters into a [collateralized debt position](mirrored-assets-massets.md#collateralized-debt-position) \(CDP\) in order to obtain newly minted tokens of an mAsset. CDPs can accept collateral in the form of ETH, mAssets, or whitelisted collateral and must maintain a collateral ratio above the mAsset's minimum multiplied by a premium rate for each collateral type \(set by governance\). 

A **shorter** is a user that enters into the same CDP but to sell the minted tokens immediately and get newly minted [sLP tokens](staking-tokens-lp-and-slp.md#slp-tokens-short-tokens). sLP token can be staked to earn MIR reward when there is a price premium for Ethereumswap price compared to the oracle price. 

Therefore, shorters effectively take a short position against the reflected asset's price direction.  
Excess collateral can be withdrawn as long as the CDP's collateral ratio remains above the minimum. Minters can adjust the CDP's collateral ratio by burning mAssets or depositing more collateral.

### Liquidity Provider

A **liquidity provider** adds equal amounts of an mAsset and ETH to the corresponding Ethereumswap pool, which increases liquidity for that market. This process rewards the liquidity provider newly minted [LP tokens](staking-tokens-lp-and-slp.md#lp-tokens), which represent the liquidity provider's share in the pool and also provide rewards from the pool's trading fees. LP tokens can be burned to reclaim the share of mAssets and ETH from the pool.

### Staker

A **staker** is a user that stakes either LP tokens or sLP tokens \(with the [Staking contract](../contracts/staking.md)\) or MIR tokens \(with the [Gov contract](../contracts/gov.md)\) in order to earn staking rewards as MIR tokens. Whereas LP and sLP token stakers earn rewards from new MIR tokens from inflation, MIR token stakers earn staking rewards from CDP withdrawal fees.

If the user has staked MIR tokens, they are eligible to participate in governance and receive voting power weighted by the amount of their total staked MIR. [Governance](governance/) is the process through which new mAssets get whitelisted and protocol parameters can be altered.

LP Tokens can be unstaked at any time, but MIR tokens can only be unstaked when they are not used to represent a vote on a pending governance poll.

### Oracle Feeder

An **oracle feeder** is a designated Ethereum account responsible for providing an accurate and up-to-date price feed for a specific mAsset or whitelisted collateral and is the sole party that is permitted to update the registered reported price of


## Tokens

There are several tokens involved in Mirror Protocol:

| Token Name | Function | Type |
| :--- | :--- | :--- |
| TerraUSD \(UST\) | Stablecoin | Native Terra asset |
| [Mirrored Assets](mirrored-assets-massets.md) \(mAssets\) | Synthetic Asset | Terraswap CW20 Token |
| [Mirror Token](mirror-token-mir.md) \(MIR\) | Staking, Governance | Terraswap CW20 Token |
| [LP Tokens](staking-tokens-lp-and-slp.md#lp-tokens) | Staking | Terraswap CW20 Token |
| [sLP Tokens](staking-tokens-lp-and-slp.md#slp-tokens-short-tokens) | Staking | Terraswap CW20 Token |

