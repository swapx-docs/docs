# swap V3 合约 API 文档

swap V3 合约交互的详细信息，涵盖了代币交换以及询价的方法。
<!-- ```text
合约地址
testnet: 0x6F94E2E94A492De5aaDCaAA1bDCCdDd79df21f3a

; mainnet: 0x216BC88DE32E256e598eD8B0Dc9a7c6b835208BD
``` -->

## 1. `exactInput`

### 方法说明：
`exactInput` 方法用于执行代币交换，用户指定了输入的数量，系统会根据当前的市场价格返回相应数量的输出代币。

### 请求参数：
- `params` (`ExactInputParams`): 交换的参数结构体，包含输入代币、输出代币、路径等信息。

`ExactInputParams` 结构体字段：
- `path` (`bytes`): 交换路径，包括输入代币和输出代币的地址以及中间代币地址。
- `recipient` (`address`): 交易的接收地址。
- `amountIn` (`uint256`): 输入的代币数量。
- `amountOutMinimum` (`uint256`): 最小输出代币数量，防止滑点过大导致交易失败。
- `deadline` (`uint256`): 交易的截止时间戳，防止交易过期。

### 返回值：
- `amountOut` (`uint256`): 实际获得的输出代币数量。

---

## 2. `exactOutput`

### 方法说明：
`exactOutput` 方法用于执行代币交换，用户指定了输出的数量，系统会根据当前的市场价格计算出相应的输入数量。

### 请求参数：
- `params` (`ExactOutputParams`): 交换的参数结构体，包含输入代币、输出代币、路径等信息。

`ExactOutputParams` 结构体字段：
- `path` (`bytes`): 交换路径，包括输入代币和输出代币的地址以及中间代币地址。
- `recipient` (`address`): 交易的接收地址。
- `amountOut` (`uint256`): 输出的代币数量。
- `amountInMaximum` (`uint256`): 最大输入代币数量，防止超出预期的输入数量。
- `deadline` (`uint256`): 交易的截止时间戳，防止交易过期。

### 返回值：
- `amountIn` (`uint256`): 实际使用的输入代币数量。

---

## 3. `exactInputSingle`

### 方法说明：
`exactInputSingle` 方法用于执行代币交换，用户指定了输入代币的数量，并且交换路径中只有两个代币（单一交换），即从一个代币到另一个代币。

### 请求参数：
- `params` (`ExactInputSingleParams`): 交换的参数结构体，包含输入代币、输出代币、路径等信息。

`ExactInputSingleParams` 结构体字段：
- `tokenIn` (`address`): 输入代币地址。
- `tokenOut` (`address`): 输出代币地址。
- `recipient` (`address`): 交易的接收地址。
- `amountIn` (`uint256`): 输入的代币数量。
- `amountOutMinimum` (`uint256`): 最小输出代币数量，防止滑点过大导致交易失败。
- `deadline` (`uint256`): 交易的截止时间戳，防止交易过期。
- `sqrtPriceLimitX96` (`uint160`): 价格限制，防止滑点过大（如果为0，则不限制）。

### 返回值：
- `amountOut` (`uint256`): 实际获得的输出代币数量。

---

## 4. `exactOutputSingle`

### 方法说明：
`exactOutputSingle` 方法用于执行代币交换，用户指定了输出的数量，并且交换路径中只有两个代币（单一交换），即从一个代币到另一个代币。

### 请求参数：
- `params` (`ExactOutputSingleParams`): 交换的参数结构体，包含输入代币、输出代币、路径等信息。

`ExactOutputSingleParams` 结构体字段：
- `tokenIn` (`address`): 输入代币地址。
- `tokenOut` (`address`): 输出代币地址。
- `recipient` (`address`): 交易的接收地址。
- `amountOut` (`uint256`): 输出的代币数量。
- `amountInMaximum` (`uint256`): 最大输入代币数量，防止超出预期的输入数量。
- `deadline` (`uint256`): 交易的截止时间戳，防止交易过期。
- `sqrtPriceLimitX96` (`uint160`): 价格限制，防止滑点过大（如果为0，则不限制）。

### 返回值：
- `amountIn` (`uint256`): 实际使用的输入代币数量。


## 5. `quoteExactInputSingle` 

### 方法说明

`quoteExactInputSingle` 方法是 router 合约中的一个函数，用于计算在单一交易路径下，通过输入指定数量的单一代币所能获得的输出代币数量。此方法帮助用户预估交易结果，以便在实际交易前避免滑点过大。

该方法通过提供输入代币数量 (exact input)，并计算通过指定的交易路径 (例如 `tokenIn` -> `tokenOut`) 能得到的输出代币数量。该函数通常用于计算交易费用、滑点等参数。


### 请求参数：
- `tokenIn` (`address`): 输入代币的地址，表示要交换的代币类型。
- `tokenOut` (`address`): 输出代币的地址，表示兑换后的代币类型。
- `fee` (`uint24`): 交换池的费用率 (例如，`500` 表示 0.05% 的费用率，`3000` 表示 0.3%)。 
- `amountIn` (`uint256`): 输入代币的数量，即用户希望交换的数量。
- `sqrtPriceLimitX96` (`uint160`): 价格限制，表示输出代币与输入代币的价格上限。通常传入 `0` 以表示不设置限制。

### 返回值说明

- `amountOut`(`uint256`): uint256类型的值，表示根据提供的输入代币数量和交易路径，所能获得的输出代币数量。此返回值是一个经过当前池子流动性和价格模型计算的结果。


## 6. `quoteExactOutputSingle`

### 方法说明：
`quoteExactOutputSingle` 方法用于估算为了获得指定的输出数量，需要投入的输入代币数量。此方法使用单一交换路径（即两个代币的直接交换），不考虑实际交易的执行，只返回理论上的估算输入数量。

### 请求参数：
- `tokenIn` (`address`): 输入代币的地址。
- `tokenOut` (`address`): 输出代币的地址。
- `fee` (`uint24`): 交换池的费用率 (例如，`500` 表示 0.05% 的费用率，`3000` 表示 0.3%)。 
- `amountOut` (`uint256`): 期望获得的输出代币数量。
- `sqrtPriceLimitX96` (`uint160`): 价格限制，防止滑点过大。如果为0，则不限制价格。

### 返回值：
- `amountIn` (`uint256`): 为了获得指定数量的输出代币所需的输入代币数量。

## 7. `createPool`

### 方法说明

`createPool` 方法用于为两个 ERC-20 代币创建一个新的流动性池。创建池子时需要指定手续费层级。此方法返回新创建池子的地址。

### 参数说明

- `tokenA` (`address`): 第一个 ERC-20 代币的地址。
- `tokenB` (`address`): 第二个 ERC-20 代币的地址。  
- `fee` (`uint24`): 池子的手续费层级，通常有：`500`（0.05%），`3000`（0.3%），`10000`（1%）。 

### 返回值说明

- `pool` (`address`): 新创建的流动性池的地址。
