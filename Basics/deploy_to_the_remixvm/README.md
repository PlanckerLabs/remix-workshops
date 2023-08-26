在前一章中，我们编译了一个合约 - 也就是说Solidity代码已经被转换成了以太坊虚拟机（EVM）字节码片段。

现在我们将把该代码部署到测试区块链上。

1. 点击“部署和运行”图标![deploy & run icon](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_to_the_remixvm/images/run.png "deploy & run icon")。

2. 从环境下拉菜单中选择**Remix VM**。

3. 点击“部署”按钮（或展开视图中的“交易”按钮）。
 
4. 您已将编译后的合约部署到Remix VM上 - 这是一个在浏览器窗口内运行的模拟区块链。Remix VM是简单、快速的测试链。如果您熟悉Truffle，您会发现它与Ganache非常相似。这不是那么真实的链，因为您不需要批准每个交易。

您可以部署到其他测试链或主网。但要做到这一点，您需要连接到另一个**环境** - 如Injected Provider。当使用Injected Provider时，您需要安装MetaMask（或类似钱包）。 MetaMask是一个浏览器插件钱包。
