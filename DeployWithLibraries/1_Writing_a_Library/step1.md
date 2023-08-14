A libraries looks like a **contract** but use the keyword `library` 

库通常是一个部署在区块链上的函数集合，任何合约都可以使用它们.  因为库已经部署在区块链上了，所以使用库能够节省许多部署合约的成本

In the following contract:
 - Make a library with the name `LibraryForTest`. 
 
 可以将库与另一个合约放在同一个文件中。  So put the library below the contract. 
 
 This library should have a method called `getFromLib` method which returns `3`.
 
 - Update the `get` method in the `test` contract to use the `LibraryForTest` library.   The function `get` should return the value it receives from `getFromLib`.

 ---------

You can find more info about libraries in <a href="https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries" target="_blank">this section of the Solidity Docs</a>.
