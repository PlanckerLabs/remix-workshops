ERC721 是一个管理以太坊区块链上非同质化代币(NFT)的代币合约标准。

每个非同质化代币都是独一无二且不可互换的。NFT可以具有不同的属性、行为或权利。非同质化代币用于表示对唯一数字和实物资产（如艺术品、收藏品或房地产）的所有权。

如果你想了解更多关于 ERC721 代币标准的信息,可以参考它的 <a href="https://eips.ethereum.org/EIPS/eip-721" target="_blank">以太坊改进提案</a>中的规范.

## 接口
ERC721 标准比 ERC20 标准更复杂,它具有可选的扩展。符合 ERC721 的合约必须至少实现 ERC721 和 ERC165 接口,我们将在本节中查看这些接口。

此接口（第11行）是<a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/IERC721.sol" target="_blank">OpenZeppelin</a>提供的开源合约库之一。

## 基础IERC721函数
符合ERC721标准的合约必须实现以下函数：

### balanceOf
函数`balanceOf`(第 30 行)返回地址为`owner`的账户拥有的代币数量。

### ownerOf
函数`ownerOf`（第39行）返回持有`tokenId`的账户地址。

### safeTransferFrom
函数`safeTransferFrom`（第55行）将`tokenId`的所属权从地址`from`拥有者转移到地址`to`拥有者名下.

该函数`safeTransferFrom`（第137行）与函数`safeTransferFrom`（第55行）几乎相同。唯一的区别是这个函数有一个非空的 payload `data`。

如果一个智能合约要接收转账,它必须实现 ERC721TokenReceiver 接口。这将确保合约可以处理 ERC721 代币转账,并防止代币被锁定在无法处理的合约中。

### transferFrom
函数`transferFrom`（第55行）将`tokenId`所属权从地址`from`拥有者转移到地址`to`拥有者名下.

**建议尽可能使用 safeTransferFrom 而不是 transferFrom。**
`transferFrom`函数不安全,因为它不会检查接收转账的智能合约是否实现了`ERC721TokenReceiver`接口并且能够处理 ERC721 代币。

## 高级 IERC721 函数
### approve
函数`approve`(第 94 行)允许地址为`to`的账户代表调用该函数的账户管理 id 为`tokenId`的代币。

### getApproved
函数`getApproved`（第103行）返回获得批准管理id为`tokenId`的token的操作者地址（return var `operator`）。

### setApprovalForAll
函数`setApprovalForAll`(第 115 行)根据指定的地址(输入参数 - `operator`)为账户设置管理其所有代币的权限(`_approved`)。

### isApprovedForAll
如果地址`operator`的账户已获得管理拥有者`owner`持有的token权限，则函数`getApproved`（第103行）返回布尔值 true。

## IERC721 Events
ERC721合约还必须发出以下事件：

### Transfer
当id为`tokenId`的token从地址`from`转移到地址`to`时，必须发出`Transfer`事件（第15行）。

### Approval
当具有地址`owner`的账户批准地址`spender`的账户代表其管理id为`tokenId`的token的权限时，必须发出`Approval`事件（第20行）。

### ApprovalForAll
当拥有者`owner`授予或删除操作员，管理其所有token的权限时，必须发出`ApprovalForAll`事件（第25行）。

## IERC165
为了支持 ERC-165 标准,ERC721 代币合约还必须实现 IERC165 接口(第 79 行)。

通过实现ERC165接口，合约可以声明对特定接口的支持。想要与另一个合约交互的合约可以在进行交易(例如,向可能不支持的合约发送代币)之前查询另一个合约是否支持该接口。

IERC721接口导入（第6行）并继承（第11行）了IERC165接口。

以下是<a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZeppelins实现</a>ERC165接口的方式：

```
interface IERC165 {
    function supportsInterface(bytes4 interfaceId) external view returns (bool);
}
```

例如，在EIP721中指定的ERC721界面的ERC165标识符为“0x80ac58cd”。了解如何计算接口标识符以及有关 ERC165 的更多信息,请参见其 <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">改进提案</a>.

## 其他接口
必须实现<a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a>接口才能接受安全转移。

在EIP721中指定了两个可选扩展名用于ERC721合约：

IERC721Enumerable使合约能够发布其完整的代币列表并使用户可以发现它们。

IERC721Metadata使合约能够将附加信息与代币关联。我们将在下一节中更详细地了解这个功能。

