---
title: "What is Liquidity"
description: ""
sidebar_position: 1
---
# What is Liquidity

## Liquidity
The liquidity of a decentralized exchange (DEX) is fundamentally different from that of a traditional centralized exchange (CEX). It does not rely on order books and market makers, but rather uses liquidity pools and automated market makers (AMM) algorithms to achieve transactions.
## Liquidity Pool
A liquidity pool is a mechanism in decentralized exchanges (DEX) and some centralized exchanges (CEX) that facilitates transactions by pooling funds (liquidity) provided by users, enabling buyers and sellers to complete transactions efficiently and at low cost. Liquidity pools are a core component of the automated market maker (AMM) model.

## Key indicators of DEX liquidity

<table><thead><tr><th width="178">Indicator</th><th width="138">Description</th><th width="182">Importance</th></tr></thead><tbody><tr><td>Total locked value (TVL)</td><td>Total amount of funds deposited in the liquidity pool</td><td>The higher the TVL, the stronger the liquidity</td></tr><tr><td>Trading volume (Volume)</td><td>24 The total transaction volume of the pool within an hour</td><td>Reflects the market activity</td></tr><tr><td>Spread</td><td>The difference between the buying price and the selling price</td><td>The smaller the spread, the better the liquidity</td></tr><tr><td>Slippage</td><td>Price deviation caused by large transactions</td><td>Low slippage indicates that the pool is deep</td></tr></tbody></table>

## Sources of DEX liquidity
**Liquidity Providers (LPs)**

Role: Ordinary users or institutions deposit assets into the liquidity pool.

Income:
Transaction fees (such as Uniswap charges 0.3%, which is distributed to LPs)

Liquidity mining rewards (such as token incentives such as SUSHI, CAKE, etc.)

**Market-making strategy optimization**

Centralized liquidity (such as Uniswap V3): Allow LPs to provide liquidity in a specific price range to improve capital efficiency.
Dynamic fees: adjust fees based on market fluctuations (such as increasing fees for high-frequency trading).

## Advantages and disadvantages of DEX liquidity
✅ Advantages
* No permission required: Anyone can become a liquidity provider (LP).
* Anti-censorship: No centralized institution controls, and transactions cannot be tampered with.
* 24/7 operation: Smart contracts are automatically executed and are not subject to traditional market time constraints.

❌ Challenges
* Impermanent loss (IL): LPs may lose money when the price of tokens in the pool fluctuates.
* Inefficient capital utilization: Some AMM models (such as Uniswap V2) have low capital utilization.
* Smart contract risks: Hacker attacks or code vulnerabilities may lead to capital losses (such as the Nomad bridge attack in 2022).

## How to evaluate the liquidity of DEX?
Check TVL and volume (such as DeFiLlama data)

Test transaction slippage (try large transactions to observe the price impact)

Analyze the depth of the liquidity pool (order book or AMM curve distribution)

Compare different DEXs (such as Uniswap vs. SushiSwap vs. Curve vs. SwapX)

## Summary

DEX liquidity relies on liquidity pools + AMM algorithms, not traditional market makers.
Liquidity providers (LPs) are the core role, earning income by depositing funds, but also bear the risk of impermanent loss.
To measure liquidity, you need to pay attention to indicators such as TVL, transaction volume, slippage, and choose a pool with sufficient depth.

The liquidity model of DEX is the cornerstone of the DeFi revolution. Despite the challenges, its openness and innovation are reshaping the future of the financial market.

Now that we have some basic understanding of liquidity, let's [go here](../add/liquidity.md) to learn how to add/remove liquidity.