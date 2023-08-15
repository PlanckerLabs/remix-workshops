Now that we know how to query simple data, let's try a more complex query.  

This is a contract deployed to the mainnet - at this address: <a href="https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#code" target="_blank">https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#code</a>

We are going to query the contract to find the name of it's token.  

The **name** variable is a state variable of the contract. 

To access this **mainnet** contract, we need to do some setup.
1. Switch to the mainnet in metamask.
2. You'll probably need to refresh Remix.
3. As a result of the refresh, you may need to reload this tutorial too.
4. Go to Deploy & Run and switch to **Injected Web3**.

**Using Web3**
In the script, queryContract.js, we need to instantiate a new instance of web3.eth.Contract object.  For this we need to grab the contract's ABI and its address.  The source code & ABI is available in etherscan because the contract's developer intentionally published it.

In etherscan, we can see that its name is **TetherToken**.  Scrolling down to the TetherToken contract in the source code section of etherscan, we can see the state variables for the contract - the first of which is named **name**. 

There are a few syntactic hoops to jump through to return the value of the state variable.  
- 为了调用public状态变量所自动生成的get函数，你需要将这个状态变量当做一个函数（在变量名后加括号），然后使用call进行调用
