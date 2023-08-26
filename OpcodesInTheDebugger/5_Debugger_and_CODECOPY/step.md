从Remix终端，找到部署合约的交易并单击`Debug`。

在编辑器的滚动槽中,在 `s = _o`  这行设置一个断点, 然后点击 `Jump to the next Breakpoint` (右下角的按钮)。

点击`Step into`，沿着操作码移动，直到达到`SSTORE`。

`SSTORE` 是将值 `_o` 存储到 storage 中的操作码。让我们继续看 `CODECOPY`。
