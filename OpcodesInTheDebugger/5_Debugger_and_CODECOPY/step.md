From the Remix terminal, identify the transaction that deployed the contract and click `Debug`

在编辑器的滚动槽中,在 `s = _o`  这行设置一个断点, 然后点击 `Jump to the next Breakpoint` (右下角的按钮)。

Click on `Step into`, to move along the opcodes until you reach `SSTORE`. 

`SSTORE` 是将值 `_o` 存储到 storage 中的操作码。让我们继续看 `CODECOPY`。
