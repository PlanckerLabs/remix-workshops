In this section, we will create a function to start the auction and a function to bid on the NFT.

### Start
We use some control structures to check if necessary conditions are met before we let the seller start the auction.

First, we check if the auction has already started (line 49). If it has started and our state variable `started` returns `true` we exit the function and throw an exception.

The second condition we check for is whether the seller is executing the function (line 50). We have already created a function to store the seller's address when they deploy the contract in the `seller` state variable and can now check if the account executing the start function is the seller. If not we throw an exception.

Next, we want to transfer the NFT that is up for auction from the seller to the contract (line 52).
We set the state variable `started` to `true` (line 53), and create an end date for the auction (line 54). In this case, it will be seven days from when the start function has been called. We can use a suffix like `days` after a literal number to specify units of time. If you want to learn more about time units have a look at the <a href="https://docs.soliditylang.org/en/latest/units-and-global-variables.html#time-units" target="_blank">solidity documentation</a>.

Finally, we will emit our `Start()` event (line 56).

### Bid
Before the function caller can make a bid, we need to be sure that certain conditions are met. The auction needs to have started (line 60), the auction can not have ended (line 61) and the bid (the value attached to the call) needs to be higher than the current highest bid (line 62).

Now we want to store the bid of the current highest bidder before we make a new bid. 
First, we check if there is a bidder (line 64). If this function call is the first bid then the next line would be irrelevant.
我们的mapping `bids` (第34行)中，使用竞价人的`地址`作为map的键，使用竞价人在撤回前的出价的ETH金额作为map的值
If there is a bidder, we add the last bid (`highestBid`) of the `highestBidder` to the total value of the bids they have made (line 65) before withdrawing.
We store the bids 因为我们希望当竞价人不再是最高竞买者时可以提取他们的出价金额

Next, we set the `highestBidder` to the account calling the function (line 68), and the `highestBid` to their bid, 金额为该合约调用所发送的金额(第69行)。

Finally, we emit the `Bid` event (line 71).

## ⭐️ Assignment
1. Deploy an NFT contract. You can use the NFT contract that we create in our "Solidity NFT Course" Learneth course.

2. Mint yourself an NFT with the tokenId 0.

3. Deploy this EnglishAuction contract. Use the address of the NFT contract as an argument for the `_nft` parameter, 0 for `_nftId`, and 1 for `_startingBid`.

4. Call the `approve` function of your NFT contract with the address of the auction contract as an argument for the `to` parameter, and 0 for `tokenId`. This will allow the contract to transfer the token to be auctioned.

5. Call the `start` function of your auction contract. If you call the `started` function now, it should return `true`. If you call the `highestBid` function it should return 1.

6. Set the value that you can attach to transactions to 3 Wei and call the `bid` function of the auction contract. If you call the `highestBid` function it should now return 3.