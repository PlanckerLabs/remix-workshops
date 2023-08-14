ERC721 是一个管理以太坊区块链上非同质化代币(NFT)的代币合约标准。

Each non-fungible token is unique and not interchangeable. NFTs can have different properties, behavior, or rights. Non-fungible tokens are used to represent ownership of unique digital and physical assets like art, collectibles, or real estate.

如果你想了解更多关于 ERC721 代币标准的信息,可以参考它的 <a href="https://eips.ethereum.org/EIPS/eip-721" target="_blank">以太坊改进提案</a>中的规范.

## Interface
ERC721 标准比 ERC20 标准更复杂,它具有可选的扩展。符合 ERC721 的合约必须至少实现 ERC721 和 ERC165 接口,我们将在本节中查看这些接口。

This interface (line 11) is part of the open-source contract library provided by <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/IERC721.sol" target="_blank">OpenZeppelin</a>.

## Basic IERC721 Functions
Contracts compliant with the ERC721 standard have to implement the following functions:

### balanceOf
函数`balanceOf`(第 30 行)返回地址为`owner`的账户拥有的代币数量。

### ownerOf
The function `ownerOf` (line 39) returns the address `owner` of the account that holds the token with the id `tokenId`.

### safeTransferFrom
The function `safeTransferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

The function `safeTransferFrom` (line 137) is almost identical to the function `safeTransferFrom` (line 55) .唯一的区别是这个函数有一个非空的 payload `data`。

如果一个智能合约要接收转账,它必须实现 ERC721TokenReceiver 接口。这将确保合约可以处理 ERC721 代币转账,并防止代币被锁定在无法处理的合约中。

### transferFrom
The function `transferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

**It is recommended to use safeTransferFrom instead of transferFrom whenever possible.**
`transferFrom`函数不安全,因为它不会检查接收转账的智能合约是否实现了`ERC721TokenReceiver`接口并且能够处理 ERC721 代币。

## 高级 IERC721 函数
### approve
函数`approve`(第 94 行)允许地址为`to`的账户代表调用该函数的账户管理 id 为`tokenId`的代币。

### getApproved
The function `getApproved` (line 103) returns the address of the account (return var `operator`) that is approved to manage the token with the id `tokenId`.

### setApprovalForAll
函数`setApprovalForAll`(第 115 行)根据指定的地址(输入参数 - `operator`)为账户设置管理其所有代币的权限(`_approved`)。

### isApprovedForAll
The function `getApproved` (line 103) returns the boolean true if the account with the address `operator` is approved to manage all tokens of the account with the address `owner`.

## IERC721 Events
ERC721 contracts must also emit the following events:

### Transfer
The `Transfer` event (line 15) must be emitted when the token with the id `tokenId` is transferred from the account with the address `from` to the account with the address  `to`.

### Approval
The `Approval` event (line 20) must be emitted when the account with the address `owner` approves the account with the address `spender` to manage the token with the id `tokenId` on its behalf.

### ApprovalForAll
The `ApprovalForAll` event (line 25) must be emitted when the account with the address `owner` gives or removes the permission (`_approved`) of the account with the address `operator` to manage all its tokens.

## IERC165
为了支持 ERC-165 标准,ERC721 代币合约还必须实现 IERC165 接口(第 79 行)。

With the implementation of the ERC165 interface, contracts can declare the support of specific interfaces. 想要与另一个合约交互的合约可以在进行交易(例如,向可能不支持的合约发送代币)之前查询另一个合约是否支持该接口。

Our IERC721 interface here imports (line 6) and inherits (line 11) from the IERC165 interface.

This is how <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZeppelins implementation</a> of the ERC165 interface looks like:

```
interface IERC165 {
    function supportsInterface(bytes4 interfaceId) external view returns (bool);
}
```

For example, the ERC165 identifier for the ERC721 interface as specified in the EIP721 is “0x80ac58cd”. 了解如何计算接口标识符以及有关 ERC165 的更多信息,请参见其 <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">改进提案</a>.

## Other interfaces
The <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a> interface must be implemented to accept safe transfers.

There are two optional extensions for ERC721 contracts specified in the EIP721:

IERC721Enumerable enables a contract to publish its full list of tokens and make them discoverable.

IERC721Metadata enables a contract to associate additional information to a token. We will have a more detailed look into this in the next section.
