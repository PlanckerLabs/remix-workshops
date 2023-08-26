元数据扩展是可选的。它允许我们向ERC721代币添加附加信息。我们可以指定名称、符号和URI（统一资源标识符），该URI可以指向一个文件，在其中以JSON格式添加更多信息。

## ERC721元数据函数

### name
函数`name`(第 16 行)返回代币集合的名称。代币集合意味着使用你的 ERC721 代币合约实现创建的所有代币。此集合中的每个代币都具有此名称,而不管其 tokenId 如何。

### symbol
函数`symbol`（第21行）返回代币集合的符号。

### tokenURI
函数`tokenURI`（第26行）返回id为`tokenId`的token的URI。在这种情况下，它不是整个集合而是集合中单个代币的URI。

## ERC721 Metadata JSON Schema
tokenURI指向的文件应符合<a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">EIP-721</a>中指定的元数据JSON模式。
 
```
{
    "title": "Asset Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "type": "string",
            "description": "A URI pointing to a resource with mime type image/* representing the asset to which this NFT represents. Consider making any images at a width between 320 and 1080 pixels and aspect ratio between 1.91:1 and 4:5 inclusive."
        }
    }
}
```
根元素必须是对象类型。这个根对象应该有名为 name、description 和 image 的属性,它们应该都是字符串类型。

ERC721 标准非常灵活, tokenURI 不需要指向一个 JSON 文档,并且 JSON 不需要有所有属性,而且通常还有其他附加属性。