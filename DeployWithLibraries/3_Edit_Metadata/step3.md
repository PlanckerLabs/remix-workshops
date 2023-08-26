在`sampleContract.json`文件中，`Deploy`属性包含了告知 Remix IDE 特定网络库地址的所有必要信息。

 - <address> 包含已经部署库的地址。您需要为每个网络指定这个地址。
 - `autoDeployLib`是一个布尔值，用于告诉 Remix IDE 是否应该在部署合约之前自动部署库。

如果 `autoDeployLib` 为 **true**, 这个 `<address>` 则不会被使用，Remix 将自动在部署合约之前首先部署一个新的库合约

在这个 demo 中 - 我们模拟库已经被部署的情况，因为这是更常见的情况。

所以将 VM: - entry 的`autoDeploy`设置为 false。

继续下一步。
