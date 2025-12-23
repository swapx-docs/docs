---
title: Market Maker Integration
sidebar_label: "Market Maker Integration"
sidebar_position: 4
---

# Market Maker Integration

## Basic Concepts of AMM
Market Maker Integration refers to the process of synergizing the resources and capabilities of multiple market makers (or market makers and other liquidity providers) through technology, strategy or institutional design to optimize market liquidity, improve transaction efficiency and reduce transaction costs. This concept is widely used in both traditional financial markets and crypto markets, especially in decentralized exchanges (DEX) and derivatives markets as a key mechanism.

## Core Goals of Market Maker Integration
* Improve liquidity: Reduce market bid-ask spreads and enhance transaction depth by integrating liquidity from multiple sources (such as market makers' own funds, automated market maker AMM pools, etc.).

* Optimize transaction execution: Intelligent routing technology allocates transactions to the market maker or liquidity pool with the best price based on real-time quotes to ensure that users get the best transaction price.

* Reduce transaction costs: Reduce fees and slippage costs by reducing intermediaries and competitive quotes.

* Enhanced market stability: integrated market makers can more efficiently deal with extreme market fluctuations, balance supply and demand, and prevent drastic price fluctuations

## Xone Chain Market Maker Integration

SwapX has integrated with XoneChain's market makers to help traders execute transactions at a lower cost.

Market makers operate in the following scenarios on SwapX.

**Existing AMM liquidity pool**

If SwapX's AMM already has liquidity for a specific token (such as XOC/PANDA), SwapX will request quotes for the same transaction from the market maker. SwapX's smart router will then route the transaction request to the AMM or market maker based on which liquidity source provides the best price at a specific time.

#### Currently supported assets

The following assets are currently supported, and may increase/decrease depending on the market maker:

**Xone Chian**

* **Major currencies**: XOC, WXOC, XUSD
* **Stablecoin**: USDH
* **Other popular assets**: PANDE, PHX, T1, T2, PANDA, PNUTX, PnutX, TEST, NUTX, PEPE

Please note that unlike automated market makers (AMMs), market makers cannot trade in arbitrary amounts, and the amount they are willing to execute depends on their own liquidity. Sometimes it is not uncommon for large orders to not be fully executed. We recommend that users carefully check the quotes to ensure that the price and quantity of each transaction meet their needs.