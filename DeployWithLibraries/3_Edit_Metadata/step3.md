The `Deploy` property in `sampleContract.json` contains everything you need for telling Remix IDE the address of the library for a specific network.

 - `<address>` 包含已经部署库的地址。您需要为每个网络指定这个地址。
 - `autoDeployLib` is a boolean and tells Remix IDE if it should autodeploy the library before deploying the contract.

如果 `autoDeployLib` 为 **true**, 这个 `<address>` 则不会被使用，Remix 将自动在部署合约之前首先部署一个新的库合约

在这个 demo 中 - 我们模拟已经库已经被部署的情况，因为这是更常见的情况。

So set `autoDeploy` to **false**, for the `VM:-` entry.

Move to next Step.
