# Delegate call

它是**message call**的一种特殊变体，它与我**message call**基本一致，唯一的区别是目标地址的代码是在调用合约的上下文中执行，因此**msg.sender**和**msg.value**不变。

This means that a contract can dynamically load code from a different address at runtime. 

The storage, the current address and balance still refer to the calling contract, only the code is taken from the called address. 

So when a **Proxy** delegates calls to the Logic contract, every storage modification will impact the storage of Logic contract.