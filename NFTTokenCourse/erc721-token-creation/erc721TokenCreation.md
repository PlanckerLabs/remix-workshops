在本合约中，我们使用了OpenZeppelin的ERC721代币合约实现（第4行）。

请查看他们的<a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol" target="_blank">ERC721 合约</a>实现。除了符合ERC721标准规定的功能外，该合约还提供了一些额外的函数，稍后我们将会看到。

## myToken 
我们创建了一个名为MyToken的合约（第7行），该合约继承了我们导入的OpenZepplin ERC721代币合约实现和Ownable（第4行）。如果您不记得Ownable合约，请查看ERC20扩展部分。

这个 ERC721 实现利用了 EIP 中指定的 IERC721Metadata 扩展。我们的合约继承了 `name()` 和 `symbol()` 函数,并有一个构造函数,允许在部署合约时设置它们的值(第 8 行)。
在这种情况下,我们将使用默认值。我们将代币命名为与合约相同的 `"MyToken"`,并将其符号设置为 `"MTK"`。

### baseURI
使用ERC721合约，我们能够铸造各种代币，每个代币都有自己的tokenId。正如我们在IERC721Metadata接口中看到的那样，每个代币可以拥有自己的`tokenURI`，通常指向一个JSON文件来存储元数据，例如名称、描述和图像链接。如果一个合约铸造多个代币,ERC721 实现通常会对所有代币使用相同的 URI 作为基础(`baseURI`),并仅通过在末尾连接其唯一的`tokenId`来区分它们。

在此示例中，我们将数据存储在IPFS上——关于此内容，请参见下一节。我们的baseURI是<a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a>（第11行）。通过连接操作，在id为0的代币tokenURI是<a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</a>，在id为1 的代币tokenURI是<a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</a>等等。

当使用IPFS遇到“504网关超时”错误时，您可能需要等待并重试，直到数据可用。

### safeMint
通过 safeMint 函数(第 14 行),我们可以在合约部署后使用专用的 token id 为所有者创建新代币。safeMint 函数是 OpenZeppelin 的 ERC721 实现的一部分,它允许我们安全地为地址`to`的账户铸造 ID 为`tokenId`的代币。 对于访问控制,我们使用从导入的 Ownable 访问控制合约模块中获取的`onlyOwner`修改器(第 5 行)。

在下一节中，我们将看到如何为NFT创建和托管元数据。

## ⭐️ 作业
1. 将您的合约名称更改为`Geometry`。
2. 将您的代币名称更改为`Geometry`。
3. 将您代币符号更改为`GEO`。
4. 将`_baseURI`更改为<a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/" target="_blank">https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/</a>。