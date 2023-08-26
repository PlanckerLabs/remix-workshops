以太币（ETH）是一种加密货币。以太币也用于支付使用以太坊网络的费用，例如将以太币发送到一个地址或与以太坊应用程序进行交互。

### 以太单位
为了指定一个以太单位，我们可以在数字后面添加`wei`、`gwei`或`ether`这些后缀。

#### `wei`
Wei是Ether的最小子单位，得名于密码学家[Wei Dai](https://en.wikipedia.org/wiki/Wei_Dai)。没有后缀的Ether数字被视为wei（第7行）。

#### `gwei`
1个GWei（千兆Wei）等于10^9 Wei。

#### `ether`
1个`ether`等于10^18 Wei（第11行）。

<a href="https://www.youtube.com/watch?v=ybPQsjssyNw" target="_blank">观看有关Ether和Wei的视频教程。</a>.

## ⭐️ 作业
1. 创建一个名为`oneGWei`的`public uint`，并将其设置为1 `gWei`。
2. 创建一个名为`isOneGWei`的`public bool`，并将其设置为比较操作 1 GWei 和 10 ^ 9 的结果。

提示：查看合约中如何编写gwei和ether。