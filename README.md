# Goals I want to achieve.


I have two safe(core) Account Abstraction wallets. Lets call it w1,w2.

w1 has some amount of (t1) ERC20 token .

w2 has some amount of (t2) ERC20 token .

I want w1 to place a limit order for 't2' erc20 token to w1 in exchange of 't1' erc20 token.


# Issue

The reply to the issue , 

"_hi the issue which i was facing is solved. but I want to know to sign the orders with safe account abstraction wallets._", 

I got from 0x spupport was


 "_Please, note that ERC1271 is not supported in 0xV4._

_This is something that we're working on and that if there are additional ERCs (beyond 1271) that you'd like to see supported, we're actively listening for feedback on that. Feel free to submit a feature request on our Canny page - you can find the link in the chat menu, from the 0x Dashboard._

_That being said, a workaround would be to construct the limit order, hash it to the EIP712 signing hash, and then when you go to sign it, instead of signing it, pick some numbers for r and s. Then do ecrecover to compute the "address" that signs that particular order (arbitrary values of r and s don't always recover a valid address. If that happens, try the other value of v. If that still doesn't work, increment r and try again). Then do registerAllowedOrderSigner for that address - because it isn't a real address with a private key, there's no risk that you're delegating control over your funds to some key that could be leaked or abused. The only downside is that you have to call registerAllowedOrderSigner every time you want to place a limit order._"  

I followed the above instructions. And hashed the order to EIP712 signing hash. The code snippet for this is in the 2nd file. 

Then I signed the txhash with my safe wallet. the code snippet for this is in the 1st file.

But I couldnt understand the rest of the instructions. 

Can you give me a code snippet on what to do next to successfully submit the order and fill it.
