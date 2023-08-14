In this section, we will use Metamask (an Ethereum wallet) to deploy our contract to the Rinkeby testnet of the Ethereum blockchain, mint an NFT, and look at it on the NFT marketplace OpenSea.

### 1. Install Metamask
**1.1** Go to <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** 点击下载按钮,然后点击对应你的浏览器（例如 Chrome）的安装按钮,并添加这个扩展到你的浏览器。

**1.3** Create a wallet as described.

### 2. Get testnet token for Rinkeby
In order to make transactions on the testnet, we need Ethereum testnet tokens.

**2.1** Switch your Metamask from "Ethereum Mainnetwork" to "Rinkeby Test Network".

**2.2** Go to <a href="https://faucet.paradigm.xyz/" 
target="_blank">https://faucet.paradigm.xyz/</a>, enter the address of your account and claim testnet ETH.
You could also use other ropsten faucets like <a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a> or <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>. Have a look at the faucets listed on <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> to learn more.

### 3. Contract Deployment
**3.1** 在 Remix IDE 的 "ENVIRONMENT(环境)" 下的 "DEPLOY & RUN TRANSACTIONS(部署与运行交易)"模块中,选择 "Injected Web3"。 It should then ask you to connect your account, which you should confirm. Then you should see the Rinkeby network badge under "Injected Web3".

**3.2** Deploy your token contract and confirm the transaction in Metamask.

**3.3**  Your contract should appear in the "Deployed Contracts" section.

### 4. Mint an NFT
**4.1** Expand your contract in the IDE so you can see the buttons for the functions.

**4.2** Expand the input fields next to the safeMint button. Enter the Ethereum address of the account that is connected to Remix in the “to:” input field. Enter “0” in the input field "tokenID:". Click on transact.

**4.3** 在 Metamask 中点击资产,然后点击 “导入代币” 链接,并将你合约的地址粘贴到输入字段中。你可以将小数位设为 0.

现在你应该可以在 Metamask 的“资产”视图中看到你的代币合约的名称和符号(例如 GEO)。你应该拥有这些代币中的一个。

### 5. See your NFT on OpenSea
<a href="https://opensea.io/" 
target="_blank">OpenSea </a> 是最受欢迎的 NFT 在线市场之一。OpenSea 也提供了一个版本,你可以在其中查看测试网上的资产,位于 <a href="https://testnets.opensea.io/" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** Go to <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/login</a>.

**5.2** 使用你的 Metamask 钱包连接。你应该被重定向到 OpenSea 上的你的账号 <a href="https://testnets.opensea.io/account" target="_blank">https://testnets.opensea.io/account</a> 视图,在那里你应该能够看到你的 NFT。你应该可以看到你 NFT 的图片;当你点击它时,你应该可以看到名称、描述,在属性下也可以看到你创建的属性。

如果你成功完成了这门课程并熟悉 Solidity 开发的基础知识,我们鼓励你通过 Learneth 的资源继续你的学习旅程,学习如何从零开始创建自己的 NFT 拍卖合约。
