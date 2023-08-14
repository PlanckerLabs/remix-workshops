# A Basic Generic Proxy Example

In the associated solidity file, **step4.sol**, there are 2 contracts - **ProxyContract** and **LogicContract**.

To use this system, we first deploy the LogicContract.

然后当我们去部署ProxyContract时，将LogicContract的地址作为ProxyContract构造函数的参数。

ProxyContract仅被部署过一次。

LogicContract代码将在第20行被调用。 It will be forwarded with delegate call while keeping the context of LogicContract.

In case we need to change the logic we would deploy a new LogicContract and set the address of it with setLogicContractAddress setter function.

*注意：这里使用的LogicConract不使用存储。一旦需要使用存储，实现就会变得更加复杂，*
