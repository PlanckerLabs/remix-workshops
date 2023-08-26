一个库看起来像是一个合约，但使用关键字library。

库通常是一个部署在区块链上的函数集合，任何合约都可以使用它们.  因为库已经部署在区块链上了，所以使用库能够节省许多部署合约的成本

在下面的合约中：
 - 创建一个名为`LibraryForTest`的库。

 可以将库与另一个合约放在同一个文件中。因此，请将该库放置在合约下方。

 这个库应该有一个名为`getFromLib`的方法，返回`3`。
 
 - 更新`test`合约中的`get`方法以使用`LibraryForTest`库。函数`get`应返回从`getFromLib`接收到的值。
 ---------

您可以在<a href="https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries" target="_blank">Solidity 文档</a> 中找到更多关于libraries信息。
