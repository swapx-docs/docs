# SwapX V3 智能合约

欢迎阅读 SwapX V3 智能合约文档。

此处的页面包含 SwapX V3 智能合约的指南和技术文档。您可以使用这些文档了解 V3 协议智能合约并开发链上集成。

# 指南

如果您不熟悉 SwapX 协议，我们建议您先从基本概念开始。

然后，您可以设置本地环境并执行第一次交换。

# 参考

如需深入了解，请阅读技术参考文档。

# 部署地址

|              合约              |                                                        测试网合约地址                                                        | 正式网合约地址 |
| :----------------------------: | :--------------------------------------------------------------------------------------------------------------------------: | :------------: |
|        swapx-v3-factory        | [0x71E1ec9BE75aA3aB781d71975EC8edBDE7b87C95](https://testnet.xscscan.com/address/0x71E1ec9BE75aA3aB781d71975EC8edBDE7b87C95) | [0xd357373500c6E5ce3A4CfA966b56F5241C7Af3c4](https://xonescan.com/address/0xd357373500c6E5ce3A4CfA966b56F5241C7Af3c4) |
|             wxoc9              |  [0xA88eF6A8B40c3605fFa6461a17A24dbbe2bfB046](https://testnet.xscscan.com/token/0xA88eF6A8B40c3605fFa6461a17A24dbbe2bfB046) | [0x4eabbaBeBbb358660cA080e8F2bb09E4a911AB4E](https://xonescan.com/address/0x4eabbaBeBbb358660cA080e8F2bb09E4a911AB4E) |
|           multicall3           | [0x2F5806492254769c202B6d0C39F85FCe666d08b8](https://testnet.xscscan.com/address/0x2F5806492254769c202B6d0C39F85FCe666d08b8) | [0xe39d7BCDdaBBD0526D143185Fb7b459099Fd40c9](https://xonescan.com/address/0xe39d7BCDdaBBD0526D143185Fb7b459099Fd40c9) |
|           proxyAdmin           | [0x7b29CAD056701fA106B480602F7C2397C5A622B0](https://testnet.xscscan.com/address/0x7b29CAD056701fA106B480602F7C2397C5A622B0) | [0x8C38838164A75FA944884e3AECE11A6a91F18348](https://xonescan.com/address/0x8C38838164A75FA944884e3AECE11A6a91F18348) |
|            ticklens            | [0xd357373500c6E5ce3A4CfA966b56F5241C7Af3c4](https://testnet.xscscan.com/address/0xd357373500c6E5ce3A4CfA966b56F5241C7Af3c4) | [0x74AEcb01C49179340B63D242D3F92cb5ff850f86](https://xonescan.com/address/0x74AEcb01C49179340B63D242D3F92cb5ff850f86) |
|        swapx-v3-Quoter         | [0x4eabbaBeBbb358660cA080e8F2bb09E4a911AB4E](https://testnet.xscscan.com/address/0x4eabbaBeBbb358660cA080e8F2bb09E4a911AB4E) | [0x75491D0E42D48121D865c6B8beccd70a28Cfff5a](https://xonescan.com/address/0x75491D0E42D48121D865c6B8beccd70a28Cfff5a) |
|      swapx-v3-SwapRouter       | [0xe39d7BCDdaBBD0526D143185Fb7b459099Fd40c9](https://testnet.xscscan.com/address/0xe39d7BCDdaBBD0526D143185Fb7b459099Fd40c9) | [0xCB56f3eDea7272224800C83eE958A4e4C1cb59Be](https://xonescan.com/address/0xCB56f3eDea7272224800C83eE958A4e4C1cb59Be) |
| swapx-v3-NFTDescriptorlibrary  | [0x8C38838164A75FA944884e3AECE11A6a91F18348](https://testnet.xscscan.com/address/0x8C38838164A75FA944884e3AECE11A6a91F18348) | [0xA42dD72DCDAB39e31423151cB61109Ba0f98113E](https://xonescan.com/address/0xA42dD72DCDAB39e31423151cB61109Ba0f98113E) |
| swapx-v3-NFTPositionDescriptor | [0x74AEcb01C49179340B63D242D3F92cb5ff850f86](https://testnet.xscscan.com/address/0x74AEcb01C49179340B63D242D3F92cb5ff850f86) | [0xe44e55b7f57BaEF8064ee06fF6Bccfa16D6a8cAB](https://xonescan.com/address/0xe44e55b7f57BaEF8064ee06fF6Bccfa16D6a8cAB) |
|  swapx-v3-NFTPositionManager   | [0x75491D0E42D48121D865c6B8beccd70a28Cfff5a](https://testnet.xscscan.com/address/0x75491D0E42D48121D865c6B8beccd70a28Cfff5a) | [0x5165486E99227e772bE2f81f595b5d9580BBdeE0](https://xonescan.com/address/0x5165486E99227e772bE2f81f595b5d9580BBdeE0) |
|  transparentUpgradeableProxy   | [0xCB56f3eDea7272224800C83eE958A4e4C1cb59Be](https://testnet.xscscan.com/address/0xCB56f3eDea7272224800C83eE958A4e4C1cb59Be) | [0x05ADde17e62B04AFA826A19e8435F40AF9Aea5D9](https://xonescan.com/address/0x05ADde17e62B04AFA826A19e8435F40AF9Aea5D9) |
|        swapx-v3Migrator        | [0xA42dD72DCDAB39e31423151cB61109Ba0f98113E](https://testnet.xscscan.com/address/0xA42dD72DCDAB39e31423151cB61109Ba0f98113E) | [0x2E464880f0aecF7F112b1dc2e7ef9A513878B3dE](https://xonescan.com/address/0x2E464880f0aecF7F112b1dc2e7ef9A513878B3dE) |
|        buysell                 | [0x05ADde17e62B04AFA826A19e8435F40AF9Aea5D9](https://testnet.xscscan.com/address/0x05ADde17e62B04AFA826A19e8435F40AF9Aea5D9) | [0xB395a25034Bf40Da8Ad36BB168f0D3442e1Fac6c](https://xonescan.com/address/0xB395a25034Bf40Da8Ad36BB168f0D3442e1Fac6c) |
