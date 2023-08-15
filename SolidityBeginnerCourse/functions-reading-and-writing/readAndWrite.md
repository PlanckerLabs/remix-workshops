This section will give a short introduction to functions and teach you how to use them to read from and write to a state variable.

As in other languages, we use functions in Solidity to create modular, reusable code. However, Solidity functions have some particularities. 

Solidity functions can be split into two types:
1. Functions that modify the state of the blockchain, like writing to a state variable. In this contract, the `set` function (line 9) changes the state variable `num`.
2. Functions that don't modify the state of the blockchain. These functions are marked `view` or `pure`. For example, in this contract, the `get` function (line 14) marked `view` that only returns `num` does not change the state.

为了定义一个函数，请使用`function`关键字以及一个唯一的函数名

If the function takes inputs like our `set` function (line 9), you must specify the parameter types and names. A common convention is to use an underscore as a prefix for the parameter name to distinguish them from state variables. 

如果函数不修改区块链状态，你可以将函数的可见性设置为`view`或者`pure`, 例如`get`函数。 Our `get` function also returns values, so we have to specify the return types. In this case, it's a `uint` since the state variable `num` that the function returns is a `uint`. 

We will explore the particularities of Solidity functions in more detail in the following sections.

<a href="https://www.youtube.com/watch?v=Mm6834AAY00" target="_blank">Watch a video tutorial on Functions</a>.

## ⭐️ 作业
1. Create a public state variable called `b` that is of type `bool` and initialize it to `true`.
2. Create a public function called `get_b` that returns the value of `b`.