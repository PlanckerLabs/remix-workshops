# What if we have state variables?

Things are more complicated once we need to deal with state variables.  State variable are saved to **storage**.

 `storage`: is a mapping; each value stored there is persisted and saved on chain.

*Note: 静态大小状态变量（除了映射和动态数组类型之外的所有类型）从位置0开始连续地存储在storage中。 如果可能，多个连续的小于32字节的项目将被打包到单个存储槽中。 For contracts that use inheritance, the ordering of state variables is determined by the C3-linearized order of contracts starting with the most base-ward contract*

Once we execute **delegate call**, the storage of both contracts get **"merged"** into a single messy state.

We have to "tell" ProxyContract what the **state** of the **Logic contract** looks like. 

The easiest way to do this is to create a separate contract - in this example - named **StorageContract** which will represent the **state** and which proxyContract will inherit from.
