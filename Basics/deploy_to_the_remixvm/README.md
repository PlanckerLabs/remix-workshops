在前一章中，我们编译了一个合约  - which is to say the Solidity code has been transformed into little chunks of Ethereum Virtual Machine (EVM) bytecode.

现在我们将把该代码部署到测试区块链上。

1. Click the Deploy and Run icon ![deploy & run icon](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_to_the_remixvm/images/run.png "deploy & run icon").  

2. Select one of the **Remix VM**s from the **Environment** pulldown. 

4. Click the Deploy button (or the transact button in the expanded view).

5. You have deployed your compiled contract to the Remix VM - 这是一个在浏览器窗口内运行的模拟区块链.  The Remix VM is simple, fast test chain.  如果您熟悉Truffle，您会发现它与Ganache非常相似 It is not that realistic a chain because you don't need to approve each transaction.  

You can deploy to other test chains or to the mainnet. But to do this you'd need to connect to another **environment** - like Injected Provider.  When you use Injected Provider - you need to have MetaMask (or a similar wallet) installed. MetaMask is a wallet that is a browser plugin.    
