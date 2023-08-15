In this contract, we use an ERC721 token contract implementation from OpenZeppelin (line 4). 

Have a look at their implementation of a <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol" target="_blank">ERC721 contract</a>. Apart from the functionality specified in the ERC721 standard, the contract provides additional functions which we will see in a bit.

## myToken 
We create our own contract called MyToken (line 7), which inherits (line 7) the functionality from the OpenZepplin `ERC721` token contract implementation and `Ownable` that we imported (line 4). If you don't remember the Ownable contract module, have a look at the ERC20 extensions section.

这个 ERC721 实现利用了 EIP 中指定的 IERC721Metadata 扩展。我们的合约继承了 `name()` 和 `symbol()` 函数,并有一个构造函数,允许在部署合约时设置它们的值(第 8 行)。
在这种情况下,我们将使用默认值。我们将代币命名为与合约相同的 `"MyToken"`,并将其符号设置为 `"MTK"`。

### Base URI
With an ERC721 contract, we are able to mint various tokens, each with its own tokenId. As we saw in the IERC721Metadata interface, each token can have its own `tokenURI`, which typically points to a JSON file to store metadata like name, description, and image link.
如果一个合约铸造多个代币,ERC721 实现通常会对所有代币使用相同的 URI 作为基础(`baseURI`),并仅通过在末尾连接其唯一的`tokenId`来区分它们。

In this example, we are storing our data on IPFS — more on that in the next section. Our baseURI is <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a> (line 11).
Through concatenation the tokenURI for the token with the id 0 would be <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</a> , the tokenURI for the token with the id 1 would be <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</a>, and so on.

When using IPFS and you run into "504 Gateway Time-out" errors, you might have to wait and retry until the data is available.

### safeMint
通过 safeMint 函数(第 14 行),我们可以在合约部署后使用专用的 token id 为所有者创建新代币。safeMint 函数是 OpenZeppelin 的 ERC721 实现的一部分,它允许我们安全地为地址`to`的账户铸造 ID 为`tokenId`的代币。 对于访问控制,我们使用从导入的 Ownable 访问控制合约模块中获取的`onlyOwner`修改器(第 5 行)。

In the next section, we will see how we can create and host the metadata for our NFTs.

## ⭐️ 作业
1. Rename your contract to `Geometry`.
2. Rename your token to `Geometry`.
3. Change the symbol of your token to `GEO`.
4. Change the `_baseURI` to <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/" target="_blank">https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/</a>.
