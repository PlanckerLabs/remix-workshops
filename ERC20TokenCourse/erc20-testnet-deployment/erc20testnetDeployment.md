In this section, we will use Metamask (an Ethereum wallet) to deploy our contract to a testnet of the Ethereum blockchain. This testnet behaves very similarly to the real blockchain (mainnet), but does not require real ETH to pay for transactions.

### 1. Install Metamask
**1.1** Go to <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** 点击下载按钮,然后点击对应你的浏览器（例如 Chrome）的安装按钮,并添加这个扩展到你的浏览器。

**1.3** Create a wallet as described.

### 2. Get testnet token
为了在测试网络上发送交易，我们需要以太坊测试网络的代币，您可以从 *测试网水龙头* 获取测试代币。

**2.1** Switch your Metamask network by clicking on the "Ethereum Mainnetwork" drop down and selecting "Ropsten Test Network". If you don’t see any test networks, click on the "Show/hide" link and enable "Show test networks" in the settings.

**2.2** Go to <a href="https://faucet.ropsten.be/" target="_blank">https://faucet.ropsten.be/</a>, enter the address of your account, and claim testnet ETH. You could also use other ropsten faucets like <a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.paradigm.xyz/</a> or <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>. Have a look at the faucets listed on <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> to learn more.

### 3. Deployment
Make sure the EduCoin contract is compiled.

**3.1.** 在 Remix IDE 的“ENVIRONMENT(环境)”下的“DEPLOY & RUN TRANSACTIONS(部署与运行交易)”模块中,选择 “Injected Web3”。 It will ask you to connect your account which you should confirm.

**3.2** Deploy the EduCoin contract and confirm the transaction in Metamask.

**3.3** Your contract should appear in the "Deployed Contracts" section. Copy the contract address.

**3.4** In Metamask, click on assets, then click on the "Import tokens" link, and paste the address of your contract in the input field.

You should now see a balance of 1000 EDC in your wallet.

### 4. 发送交易
**4.1** Click on the identicon (visual representation of your address) in the Metamask wallet and create a second account (Account 2).

**4.2** Copy the address of Account 2.

**4.3** Switch to the first account (Account 1) and send 250 EDC to Account 2. Check the balances of Account 1 and Account 2. 如果要使用Account2进行交易，则可能需要再次为 Account 2 添加EDU代币地址以便于导入代币，并且也需要为Account2申请测试代币。

You can also see your account balances if you look at the contract in Remix and call the `balanceOf` function using the addresses of Account 1 and Account 2.
