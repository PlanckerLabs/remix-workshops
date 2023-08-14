The metadata extension is optional. It allows us to add additional information to our ERC721 tokens. We can specify a name, a symbol, and an URI (Uniform Resource Identifier) that can point to a file where we can add even more information in the form of a JSON.

## ERC721 Metadata Functions

### name
函数`name`(第 16 行)返回代币集合的名称。代币集合意味着使用你的 ERC721 代币合约实现创建的所有代币。此集合中的每个代币都具有此名称,而不管其 tokenId 如何。

### symbol
The function `symbol` (line 21) returns the symbol of the token collection.

### tokenURI
The function `tokenURI` (line 26) returns the URI for the token with the id `tokenId`. In this case it’s not the URI of the whole collection but of an individual token in the collection.

## ERC721 Metadata JSON Schema
The file that the tokenURI points to should conform to the Metadata JSON Schema as it is specified in the <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">EIP-721</a>.
 
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
