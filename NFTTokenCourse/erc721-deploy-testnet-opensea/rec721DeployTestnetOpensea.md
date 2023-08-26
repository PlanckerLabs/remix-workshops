在本节中，我们将使用以太坊钱包Metamask来部署我们的合约到以太坊区块链上的Rinkeby测试网络，铸造一个NFT，并在NFT市场OpenSea上查看它。

### 1. 安装Metamask
**1.1** 前往<a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** 点击下载按钮,然后点击对应你的浏览器（例如 Chrome）的安装按钮,并添加这个扩展到你的浏览器。

**1.3** 按照说明创建一个钱包。

### 2. 获取Rinkeby测试网的测试代币
为了在测试网上进行交易，我们需要以太坊测试代币。

**2.1** 将您的Metamask从“Ethereum Mainnetwork”切换到“Rinkeby Test Network”。

**2.2** 前往<a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a>，输入您账户地址并领取测试网ETH。 您也可以使用其他ropsten水龙头，如<a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a> 或者 <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>。请访问<a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a>列出的水龙头列表以获取更多信息。

### 3. 合约部署
**3.1** 在 Remix IDE 的 "ENVIRONMENT(环境)" 下的 "DEPLOY & RUN TRANSACTIONS(部署与运行交易)"模块中,选择 "Injected Web3"。 然后它应该要求您连接您的账户，请确认。然后你应该在“Injected Web3”下看到Rinkeby网络标志。

**3.2** 部署您的代币合约并在Metamask中确认交易。

**3.3** 您的合约应该出现在“Deployed Contracts”部分。

### 4. 铸造 NFT
**4.1** 在 IDE 中展开您的合约，以便您可以看到函数按钮。

**4.2** 展开`safeMint`按钮旁边的输入字段。在“to:”输入字段中输入与 Remix 连接的以太坊地址。在“tokenID:”输入字段中输入“0”。点击交易。

**4.3** 在 Metamask 中点击资产,然后点击 “导入代币” 链接,并将你合约的地址粘贴到输入字段中。你可以将小数位设为 0.

现在你应该可以在 Metamask 的“资产”视图中看到你的代币合约的名称和符号(例如 GEO)。你应该拥有这些代币中的一个。

### 5. 在 OpenSea 上查看您的 NFT
<a href="https://opensea.io/" 
target="_blank">OpenSea </a> 是最受欢迎的 NFT 在线市场之一。OpenSea 也提供了一个版本,你可以在其中查看测试网上的资产,位于 <a href="https://testnets.opensea.io/" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** 前往 <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/login</a>.

**5.2** 连接你的 Metamask 钱包。你应该被重定向到 OpenSea 上的你的账号 <a href="https://testnets.opensea.io/account" target="_blank">https://testnets.opensea.io/account</a> 视图,在那里你应该能够看到你的 NFT。你应该可以看到你 NFT 的图片;当你点击它时,你应该可以看到名称、描述,在属性下也可以看到你创建的属性。

如果您已经成功完成了这门课程并熟悉Solidity开发的基础知识，我们鼓励您通过Learneth的资源学习如何从零开始创建自己的 NFT 拍卖合约，继续您的学习之旅。