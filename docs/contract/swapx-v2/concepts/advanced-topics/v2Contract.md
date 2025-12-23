# swap V2 合约 API 文档

swap V2 兑换，询价, 创建池以及提供流动性合约交互的方法。
<!-- ```text
合约地址
testnet: 0x216BC88DE32E256e598eD8B0Dc9a7c6b835208BD

mainnet: 0x216BC88DE32E256e598eD8B0Dc9a7c6b835208BD
``` -->

## 1. `swapExactTokensForTokens`

### 方法说明：
此方法用于将指定数量的输入代币交换为输出代币，并确保获得至少 `amountOutMin` 数量的输出代币。

### 请求参数：
- `amountIn` (`uint256`): 你想要交换的输入代币数量。
- `amountOutMin` (`uint256`): 最少可以获得的输出代币数量。如果实际输出代币小于此值，交易将被回滚。
- `path` (`address[]`): 交换路径，包括输入和输出代币的地址数组。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 2. `swapTokensForExactTokens`

### 方法说明：
此方法用于交换输入代币，以获得精确数量的输出代币，并确保不会支付超过 `amountInMax` 数量的输入代币。

### 请求参数：
- `amountOut` (`uint256`): 你希望获得的输出代币数量。
- `amountInMax` (`uint256`): 最多可以支付的输入代币数量。
- `path` (`address[]`): 交换路径，包括输入和输出代币的地址数组。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 3. `swapExactETHForTokens`

### 方法说明：
此方法用于将指定数量的 XOC 交换为目标代币，并确保你能获得至少 `amountOutMin` 数量的目标代币。

### 请求参数：
- `amountOutMin` (`uint256`): 最少可以获得的输出代币数量。
- `path` (`address[]`): 交换路径，包括 XOC 和目标代币的地址。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 4. `swapTokensForExactETH`

### 方法说明：
此方法用于将输入代币交换为指定数量的 XOC，并确保你不会支付超过 `amountInMax` 数量的输入代币。

### 请求参数：
- `amountOut` (`uint256`): 你希望获得的 XOC 数量。
- `amountInMax` (`uint256`): 最多可以支付的输入代币数量。
- `path` (`address[]`): 交换路径，包括输入代币和 XOCH 的地址。
- `to` (`address`): 接收 XOC 的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 5. `swapExactTokensForETH`

### 方法说明：
此方法用于将指定数量的代币交换为 XOC，并确保你能够获得至少 `amountOutMin` 数量的 XOC。

### 请求参数：
- `amountIn` (`uint256`): 你希望投入的输入代币数量。
- `amountOutMin` (`uint256`): 最少可以获得的 XOC 数量。
- `path` (`address[]`): 交换路径，包括输入代币和 XOC 的地址。
- `to` (`address`): 接收 ETH 的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 6. `swapETHForExactTokens`

### 方法说明：
此方法用于将指定数量的 XOC 交换为精确数量的目标代币，并确保你不会支付超过 `amountInMax` 数量的 XOC。

### 请求参数：
- `amountOut` (`uint256`): 你希望获得的目标代币数量。
- `amountInMax` (`uint256`): 最多可以支付的 XOC 数量。
- `path` (`address[]`): 交换路径，包括 XOC 和目标代币的地址。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- `amounts` (`uint256[]`): 交换过程中每个步骤的代币数量数组。

---

## 7. `swapExactTokensForTokensSupportingFeeOnTransferTokens`

### 方法说明：
此方法与 `swapExactTokensForTokens` 类似，但它支持处理带有手续费的代币（如具有转账税的代币）。它能够确保在代币转移过程中正确处理费用。

### 请求参数：
- `amountIn` (`uint256`): 你希望投入的输入代币数量。
- `amountOutMin` (`uint256`): 最少可以获得的输出代币数量。
- `path` (`address[]`): 交换路径，包括输入代币和目标代币的地址。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- 此方法不返回任何值。


## 8. `swapExactETHForTokensSupportingFeeOnTransferTokens`

### 方法说明：
此方法允许用户用指定数量的 XOC 交换至少一定数量的目标代币，且支持具有转账手续费的代币。它会将 XOC 存入，然后通过 V2 交易对执行代币交换。

### 请求参数：
- `amountOutMin` (`uint`): 用户愿意接受的最低输出代币数量。如果实际交换得到的代币少于该值，交易将会被撤销。
- `path` (`address[]`): 定义交换路径的地址数组。数组中的第一个代币地址必须是XOC，最后一个代币地址是用户将要获取的目标代币。
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- 此方法不返回任何值。

## 9. `swapExactTokensForETHSupportingFeeOnTransferTokens`

### 方法说明：
此方法允许用户用指定数量的代币交换至少一定数量的 XOC，且支持具有转账手续费的代币。它会将输入的代币转移到 V2 交易对，通过交换获得 XOC 并将其提取。

### 请求参数：
- `amountIn` (`uint`): 用户愿意交换的输入代币数量。
- `amountOutMin` (`uint`): 用户希望收到的最低 ETH 数量。如果实际获得的 ETH 少于该值，交易将会被撤销。
- `path` (`address[]`): 定义交换路径的地址数组。数组中的第一个代币是用户将要交换的代币，最后一个代币必须是 XOC
- `to` (`address`): 接收输出代币的地址。
- `deadline` (`uint256`): 交易的截止时间（Unix时间戳）。

### 返回值：
- 此方法不返回任何值。



## 10.`createPair` 方法

### 方法说明

`createPair` 方法用于在 Uniswap V2 中创建一个新的交易池（流动性池）。如果池子已经存在，则该方法会失败。如果两个代币之间已经有池子，则无法创建新的池子。该方法通过调用 Factory 合约来实现，Factory 合约负责管理所有的交易池。

### 参数说明

- `tokenA` (`address`): 第一个 ERC-20 代币的地址，表示池中第一个代币。
- `tokenB` (`address`): 第二个 ERC-20 代币的地址，表示池中第二个代币             |

### 返回值说明

`createPair` 方法没有直接的返回值，它的作用是成功创建一个新的交易池。如果池子创建成功，池子会存储在 **Factory** 合约中，供后续使用（如添加流动性、执行交易等）。

---

## 11. `addLiquidity` 方法

### 方法说明

`addLiquidity` 方法用于将两种 ERC-20 代币（`tokenA` 和 `tokenB`）添加到一个 Uniswap V2 流动性池中。用户通过这个方法提供一定数量的两种代币，池子则根据现有的储备量和输入数量计算并分配流动性凭证（LP token）给用户。

### 请求参数：
- `tokenA` (`address`): 第一个 ERC-20 代币的地址，即用户要提供的代币类型之一。
- `tokenB` (`address`): 第二个 ERC-20 代币的地址，即用户要提供的代币类型之二。
- `amountADesired` (`uint`): 用户希望提供的第一个代币 `tokenA` 的数量。 
- `amountBDesired` (`uint`): 用户希望提供的第二个代币 `tokenB` 的数量。 
- `amountAMin` (`uint`): 用户愿意接受的最小 `tokenA` 数量，这通常用于防止滑点过大。 
- `amountBMin` (`uint`): 用户愿意接受的最小 `tokenB` 数量，这通常用于防止滑点过大。 
- `to` (`address`): 流动性提供者的地址（通常是调用合约的地址），用于接收 LP token。 
- `deadline` (`uint`): 交易的截止时间，单位是 Unix 时间戳，超过此时间交易将失败。 

### 返回值说明

- `amountA` (`uint`): 实际添加到流动性池中的第一个代币 `tokenA` 的数量。 
- `amountB` (`uint`): 实际添加到流动性池中的第二个代币 `tokenB` 的数量。 
- `liquidity` (`uint`): 返回的流动性凭证（LP token）数量，表示用户在池中所占的份额。 


## 12. `addLiquidityETH` 方法

### 方法说明

`addLiquidityETH` 方法允许用户将 XOC 和其他 ERC-20 代币（token）添加到 V2 流动性池中。此方法类似于 addLiquidity，但支持以 XOC 作为流动性的一部分。

### 请求参数：
- `token` (`address`): 需要提供流动性的 ERC-20 代币地址。
- `amountTokenDesired` (`address`): 用户希望提供的 ERC-20 代币数量。
- `amountTokenMin` (`uint`): 用户愿意接受的最小 ERC-20 代币数量，这通常用于防止滑点过大。 
- `amountETHDesired` (`uint`): 用户希望提供的 XOC 数量。 
- `amountETHMin` (`uint`): 用户愿意接受的最小 XOC 数量，这通常用于防止滑点过大。
- `to` (`address`): 流动性提供者的地址（通常是调用合约的地址），用于接收 LP token。 
- `deadline` (`uint`): 交易的截止时间，单位是 Unix 时间戳，超过此时间交易将失败。 

### 返回值说明

- `amountToken` (`uint`): 实际添加到流动性池中的 ERC-20 代币数量。 
- `amountETH` (`uint`): 实际添加到流动性池中的 XOC 数量。 
- `liquidity` (`uint`): 返回的流动性凭证（LP token）数量，表示用户在池中所占的份额。 

## 13. `quote`
`quote` 方法是合约中的一个辅助函数，用于计算在给定的流动性池中，特定输入代币数量能够兑换到的输出代币数量。该方法的作用是根据 **恒定乘积公式 (Constant Product Formula)**，计算输入一定数量的代币时，所能获得的输出代币的数量。

池中的流动性由两个代币的储备量决定，`quote` 方法通过这些储备量来估算输入一定数量的代币时，输出代币的数量。

### 请求参数：
- `amountA` (`uint`): 输入的第一个代币的数量 (即用户想要交换的代币数量)。
- `reserveA` (`uint`): 表示池子中该代币的数量。
- `reserveB` (`uint`): 表示池子中该代币的数量。 
```text
`getReserves`方法可以获取到交易对中两个代币的储备量，例如`getReserves`返回的`_reserve0`此时代表`tokenA`的储备量，`_reserve1`此时代表`tokenB`的储备量，使用quote方法传入`_reserve0`表示`reserveA`，
`_reserve1`表示`reserveB`，此时表示输入`amountA`数量的`tokenA`代币，可以获得多少`tokenB`代币，同理使用quote方法传入`_reserve1`表示`reserveA`，`_reserve0`表示`reserveB`，此时表示输入`amountA`数量
的`tokenB`代币，可以获得多少`tokenA`代币。
```

### 返回值说明

`quote` 方法返回一个 `uint256` 类型的值，表示通过给定数量的 `amountA` 输入代币，能够兑换到的 `tokenB` 输出代币的数量。该返回值根据 Uniswap V2 的 **恒定乘积公式** 计算，公式如下：

```text
amountOut = (reserveB * amountAIn) / (reserveA + amountAIn)
```

## 12. `getReserves`

### 方法说明

`getReserves` 是 V2 交易对合约中的一个读取函数，用于获取交易对中两个代币的当前储备量。此方法返回当前交易对中两个代币的数量以及最近一次更新储备量的时间戳。此方法常用于计算交易对的价格、滑点等参数。

### 请求参数：

`getReserves` 方法无请求参数

### 返回值：
- `_reserve0` (`uint112`): 交易对中第一个代币的储备量。
- `_reserve1` (`uint112`): 交易对中第二个代币的储备量。
- `blockTimestampLast` (`uint32`): 最近一次更新储备量的时间戳（单位为秒）


## 13. `getPair`

### 方法说明

`getPair` 方法是用于获取两个代币对应的交易对合约地址的方法。每对代币（如 ETH 和 USDT）都会有一个独立的交易对合约，该合约负责维护两个代币的流动性池。

### 请求参数：

- `tokenA` (`address`): 第一个代币的地址。
- `tokenB` (`address`): 第二个代币的地址。

### 返回值：
- `pair` (`address`): 返回给定代币对的交易对合约地址。如果指定的代币对尚未存在，则返回 address(0)。
