# Testing Trading:

Login to an account with ETH. For this test, you will need more than one account ready because we will want to test both sides of trading.

For these tests, you should [create a new market](/createMarket.md) and do not provide any liquidity for that market. Remember what you entered for an expiration date/time and the settlement fee % you set during creation. We will want to verify these values on the trading page later.

For these tests, we are going to assume that Account 1 is also the Market Creator.

### Binary Market Trading
(Work in Progress...)

After creating a new binary market, navigate to the markets page and find your new market's card.

click on the "trade" button on the newly created market.

When the market trading page loads, please *verfy* the following:

*Verify:*

- [x] "Yes" is the only outcome you can select and it's pre-selected. (if you can see the order form you have a selected outcome)
- [x] Fee % shown is the settlement Fee value set (default is 2%) at creation + the current reporting fee (hardcoded to 1% in tests)
- [x] Confirm the Expiration Date/time shown is accurate to your endtime set during market creation.
- [x] clicking on the positions title should drop down an empty postitions and open orders table.
- [x] The `LAST` price value should be equal to `0.5` on a new binary market, this value is the midpoint for the market since no trades have taken place.

Using Account 1 (remember, Account 1 is the account that created the market) we will now attempt to place an order. 

Enter a number for the amount of shares you would like to buy, and enter a price between 0 and 1. 

*Verify:*

- [x] quantity cannot be 0 or negative.
- [x] limit price cannot be outside of the range for this market (0-1 in this case)
- [x] est. cost is calculated correctly (quantity * price)

Click the Review button.

*Verify:*
- [x] Outcome is labeled correctly as "yes"
- [x] quantity is accurate to what you entered
- [x] limit price is accurate to what you entered
- [x] for this trade, fee should be 0 as we are only going to be placing an order on an empty book
- [x] est. cost is still accurately calculated
- [x] Confirm that Profit Loss calculations are correct. 
- [x] your ETH balance has decreased by the amount of ETH the order cost

Note: an example of Profit Loss calculations would be doing a trade for 1 share at .9 ETH. In that case: Max Gain is .1 ETH (11.11%); Max Loss is 0.9 ETH (100%).

Click "Confirm".

Sign your transaction. 

After the transaction is complete and successful...

*Verify:*
- [x] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [x] The Order Book Chart should now show 1 order on the BID side (bottom) of the book, again confirm details.
- [x] You should see an open order row under the "Positions" section. 
- [x] The Open Order should be labeled "Yes"
- [x] The Open Order should have a positive number for quantity
- [x] The Open Order should have an average price set to the limit price of the order placed on the book.
- [x] The Open Order should have a clickable Cancel Button.

Click the Cancel button.

*Verify:*
- [x] The Open Order row should change into a purple bar
- [x] The Open Order row should say `Cancel order for N shares of "Yes" at X ETH?` Where N is the quantity of your order and X is the price.
- [x] There should be a yes and a no button on the right side of the open order row.

click no, the ribbon should disappear and the open order row should return to what it looked like prior to clicking the Cancel button.

Click Cancel.

Click Yes.

*Verify:*
- [x] you are prompted to sign a transaction to cancel the order.

Sign the transaction to cancel the order. Once succesfully complete:

*Verify:*
- [x] the order has been removed from the open order table, and our positions/orders table is empty again.
- [x] The order has been removed from the orderbook chart
- [x] The Outcome bar shows `--` across the board again except for the LAST value which should be equal to 0.5
- [x] You should have been refunded ETH that was originally taken from placing the order.

With Account 1 still, place another BUY Order. You can use whatever values you want to test with, but for the sake of the walk through I'm going to use an example of 10 shares for 0.5 ETH.

After placing the order...

*Verify:*
- [x] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [x] The Order Book Chart should now show 1 order on the BID side (bottom) of the book, again confirm details.
- [x] You should see an open order row under the "Positions" section. 
- [x] The Open Order should be labeled "Yes"
- [x] The Open Order should have a positive number for quantity
- [x] The Open Order should have an average price set to the limit price of the order placed on the book.
- [x] The Open Order should have a clickable Cancel Button.

Login to Account 2. Account 2 should be an account with ETH that has never traded on Augur before.

Navigate back to the market page.

*Verify:* 
- [x] Account 1's Order is displayed accurately on the order book
- [x] The Outcome bar should be showing Bid QTY as 10 (for out example, again you can use whatever number you want)
- [x] The Outcome bar should be showing Best Bid as equal to `0.5`

Click on the `Sell` button on the order form.

Enter the same values you entered in the previous order (if following the example, 10 quantity, .5 limit price)

Click Review and then click Confirm.

*Verify:*
- [x] The "Approve Augur" modal displays on the screen

Click the "Approve" button.

*Verify:*
- [x] You are prompted to sign an approval transaction

Sign the approval transaction.

*Verify:*
- [x] You are prompted to sign the order transaction immediately after signing approval.

Sign the trade transaction.

After the transaction completes, we should now have a position, since this trade should result in a completely filled order from Account 1.

while still logged into Account 2...

*Verify:*
- [x] The Positions Table now has 1 row showing a "Yes" position
- [x] The Position should have a negative number for Quantity
- [x] The Position should show the purchase price


### Categorical Market Trading

(Work in Progress....)

### Scalar Market Trading

(Work in Progress....)


[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)