# Testing Trading:

Login to an account with ETH. For this test, you will need more than one account ready because we will want to test both sides of trading.

For these tests, you should [create a new market](/createMarket.md) and do not provide any initial liquidity for that market. Remember what you entered for an expiration date/time and the settlement fee % you set during creation. We will want to verify these values on the trading page later.

For these tests, we are going to assume that Account 1 is also the Market Creator.

### Binary Market Trading

After creating a new binary market, navigate to the Market List page and find your new market's card.

Click on the "trade" button on the newly created market.

When the market trading page loads, please *verfy* the following:

*Verify:*

- [X] "Yes" is the only outcome you can select and it's pre-selected. (If you can see the order form and candlestick chart, the outcome is selected.)
- [X] Fee % shown in the header is the Settlement Fee value set at market creation + the current reporting fee (hardcoded to 1% in tests).
- [X] Confirm the Expiration Date/time shown is accurate to your endtime set during market creation. It should be formatted to the user's current timezone.
- [X] Clicking on the My Positions title (underneath Outcomes) should drop down the empty positions/orders null state: "No positions or open orders".
- [X] The `LAST` price value on the "Yes" outcome should be equal to `0.5` on a new binary market. (This value is the midpoint for the market since no trades have taken place.)

Switch to an account with 0 ETH.

- [X] Verify that you are shown the "Add funds to begin trading." message and "Add Funds" button where the order form is normally displayed.
- [X] Verfiy that clicking on the "Add Funds" button brings you to the Account: Deposit page.

Switch back to Account 1 (the account that created the market). We will now attempt to place an order. 

Enter a number for the amount of shares you would like to buy, and enter a price between 0 and 1. 

*Verify:*

- [ ] [ch10925](https://app.clubhouse.io/augur/story/10925/making-an-order-with-0-shares-is-not-prevented-well)Quantity cannot be 0 or negative.
- [ ] [ch10925](https://app.clubhouse.io/augur/story/10925/making-an-order-with-0-shares-is-not-prevented-well)Limit price cannot be outside of the range for this market (0-1 in this case)
- [X] Est. cost is calculated correctly (quantity * price)

Click the Review button.

*Verify:*
- [X] Quantity is accurate to what you entered.
- [X] Limit price is accurate to what you entered.
- [X] For this trade, the Fee should be 0 because we won't be closing shares here.
- [X] Est. cost is still accurately calculated. (quantity * price)
- [X] Confirm that Profit & Loss calculations are correct.
- [X] Hit the "Back" button. Verify the original values you entered are still there. (Then hit "Review" again.)
- [X] Click "Review" again and then submit the transaction. Verify the transaction submits successfully.

Note: an example of Profit Loss calculations would be doing a trade for 1 share at .9 ETH. In that case: Max Gain is .1 ETH (11.11%); Max Loss is 0.9 ETH (100%).

After the transaction is complete and successful:

*Verify:*
- [X] Your ETH balance has decreased by the amount of ETH the order cost. This should show both in the core stats bar and on the Account page.
- [X] The "Yes" outcome has updated to show a Bid Qty and Best Bid value that match your order details.
- [X] The Order Book Chart should now show 1 order on the BID side (bottom) of the book. Confirm details.
- [X] You should see an open order row under the "Positions" section.
- [X] The Open Order should be labeled "Yes".
- [X] The Open Order should have a positive number for quantity that matches your order.
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Click the Cancel button.

*Verify:*
- [X] The Open Order row should change into a purple bar.
- [X] The Open Order row should say `Cancel order to buy N shares of "Yes" at X ETH?` Where N is the quantity of your order and X is the price.
- [X] There should be a Yes and a No button on the right side of the open order row.
- [X] Click No. The ribbon should disappear and the open order row should return to what it looked like prior to clicking the Cancel button.
- [X] Click Cancel again, then click Yes to cancel the open order. Verify that you can submit the cancelation transaction successfully.

Once succesfully complete:

*Verify:*
- [X] the order has been removed from the open order table, and our positions/orders table is empty again.
- [X] The order has been removed from the orderbook chart
- [X] The Outcome bar shows `--` across the board again except for the LAST value which should be equal to 0.5
- [X] You should have been refunded ETH that was originally taken from placing the order. This should display both in the core stats bar and on the Account page.

With Account 1 still, place another BUY Order. You can use whatever values you want to test with, but for the sake of the walk through I'm going to use an example of 10 shares for 0.5 ETH.

After placing the order...

*Verify:*
- [X] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [X] The Order Book Chart should now show 1 order on the BID side (bottom) of the book, again confirm details.
- [X] You should see an open order row under the "Positions" section. 
- [X] The Open Order should be labeled "Yes"
- [X] The Open Order should have a positive number for quantity that matches the quantity you entered.
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Login to Account 2. Account 2 should be an account with ETH that has never traded on Augur before.

Navigate back to the market page.

*Verify:* 
- [X] Account 1's Order is displayed accurately on the order book
- [X] The Outcome bar should be showing Bid QTY as 10 (for out example, again you can use whatever number you want)
- [X] The Outcome bar should be showing Best Bid as equal to `0.5`

Click on the `Sell` button on the order form.

Enter the same values you entered in the previous order (if following the example, this should be 10 quantity, 0.5 limit price)

Click Review and then click Confirm.

`Note: the the following approval flow will only happen the first time you attempt to trade with an account that isn't Account 1. After approving one time, assuming you don't reset the docker node, you shouldn't see approval again. This is expected.`

*Verify:*
- [X] The "Approve Augur" modal displays on the screen
- [X] You can click "Approve" and sign to successfully approve the transaction.
- [X] You are prompted to sign the order transaction immediately after signing approval.

`Note: This is the end of the approval flow, anything below should happen every trade.`

Sign the trade transaction.

After the transaction completes, we should now have a position, since this trade should result in a completely filled order from Account 1.

While still logged into Account 2:

*Verify:*
- [X] The Positions Table now has a row showing a "Yes" position
- [X] The Position should have a negative number for Quantity
- [X] The Position should show the purchase price
- [X] The charts have updated to show a new candlestick
- [X] The Order Book Chart reflects that the open order is gone and has been filled.
- [X] Login to Account 1 and verify the above, but for their side of the trade.

Now log back into Account 2, navigate to the market, and place an order to `Buy` for the same values you entered previously. (10 quantity at 0.5 ETH limitPrice if using the example)

*Verify:*
- [X] You didn't send any ETH with this order (outside of gas) as you should be sending your SELL shares
- [X] The Open Order bar reflects the order we just placed
- [X] The Positions bar is unchanged despite escrowing your Shares into the open order.

Switch to Account 1 (market creator account). Navigate to the market.

Execute a `Sell` order that will fill the order on the book to `Buy` placed by Account 2. (10 quantity at 0.5 ETH limit price in example)

Once the trade completes:

*Verify:*
- [X] Account 1 also didn't send any ETH (outside of gas) to place this order
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 1 Recieved `5 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~4.925 ETH` assuming 3% settlement). 

Login to Account 2, navigate to market page.

*Verify:*
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 2 Recieved `5 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~4.925 ETH` assuming 3% settlement).
- [X] Account 1 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph
- [X] Account 2 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph

### Categorical Market Trading

After creating a new categorical market, navigate to the markets page and find your new market's card.

Click on the "trade" button on the newly created market.

When the market trading page loads, please *verfy* the following:

*Verify:*

- [X] All outcomes are listed under the outcome table, with none of them pre-selected.
- [X] The Price History chart displays.
- [X] Fee % shown is the settlement Fee value set (default is 2%) at creation + the current reporting fee (hardcoded to 1% in tests)
- [X] Confirm the Expiration Date/time shown is accurate to your endtime set during market creation.
- [X] Clicking on the positions title should drop down an empty postitions and open orders table.
- [X] The `LAST` price value should be equal to `1 / numOutcomes` on a new categorical market. (3 = .3333, 4 = .25, etc)

Using Account 1 (the account that created the market) we will now attempt to place an order.

Select one of the outcomes.

*Verify:*
- [X] The candlestick chart/market depth/order book for that outcome should display.
- [X] The Trading Form is now visible on the right hand side of your screen.

Enter a number for the amount of shares you would like to buy, and enter a price between 0 and 1. 

*Verify:*
- [X] The Trading Form displays the name of the outcome we have selected.
- [ ] [ch10925](https://app.clubhouse.io/augur/story/10925/making-an-order-with-0-shares-is-not-prevented-well)Quantity cannot be 0 or negative.
- [ ] [ch10925](https://app.clubhouse.io/augur/story/10925/making-an-order-with-0-shares-is-not-prevented-well)Limit price cannot be outside of the range for this market (0-1 in this case)
- [X] Est. cost is calculated correctly (quantity * price)

Click the Review button.

*Verify:*
- [X] Outcome is labeled correctly as the outcome you have selected.
- [X] Quantity is accurate to what you entered.
- [X] Limit price is accurate to what you entered.
- [X] For this trade, fee should be 0 because we won't be closing shares here.
- [X] Est. cost is still accurately calculated.
- [X] Confirm that Profit Loss calculations are correct. 
- [X] You can place the trade successfully.
- [X] "Order Placed" notification displays at the bottom of the Trading Form and disappears after a couple seconds.
- [X] Your ETH balance has decreased by the amount of ETH the order cost. This should display both in the core stats bar and on the Account page.

Note: an example of Profit Loss calculations would be doing a trade for 1 share at .9 ETH. In that case: Max Gain is .1 ETH (11.11%); Max Loss is 0.9 ETH (100%).

After the transaction is complete and successful:

*Verify:*
- [X] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [X] The Order Book Chart should now show 1 order on the BID side (bottom) of the book, again confirm details.
- [X] You should see an open order row under the "Positions" section. 
- [X] The Open Order should be correcty labeled for the outcome selected
- [X] The Open Order should have a positive number for quantity
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Click the Cancel button.

*Verify:*
- [X] The Open Order row should change into a purple bar
- [X] The Open Order row should say `Cancel order for N shares of "<outcome label here>" at X ETH?` Where N is the quantity of your order and X is the price.
- [X] There should be a yes and a no button on the right side of the open order row.

Click no, the ribbon should disappear and the open order row should return to what it looked like prior to clicking the Cancel button.

Click Cancel.

Click Yes.

*Verify:*
- [X] you are prompted to sign a transaction to cancel the order.

Sign the transaction to cancel the order. Once succesfully complete:

*Verify:*
- [X] the order has been removed from the open order table, and our positions/orders table is empty again.
- [X] The order has been removed from the orderbook chart
- [X] The Outcome bar shows `--` across the board again for order outcome except for the `LAST` value which should be equal to `1 / numOutcomes`
- [X] You should have been refunded ETH that was originally taken from placing the order.

With Account 1 still, place a BUY Order on an Outcome. You can use whatever values you want to test with, but for the sake of the walk through I'm going to use an example of 10 shares for 0.5 ETH.

After placing the order...

*Verify:*
- [X] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [X] The Order Book Chart should now show 1 order on the BID side (bottom) of the book, again confirm details.
- [X] You should see an open order row under the "Positions" section. 
- [X] The Open Order should be labeled with the correct outcome
- [X] The Open Order should have a positive number for quantity
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Login to Account 2. Account 2 should be an account with ETH that has never traded on Augur before.

Navigate back to the market page and select the same outcome as before.

*Verify:* 
- [X] Account 1's Order is displayed accurately on the order book
- [X] The Outcome bar should be showing Bid QTY as 10 (for our example, again you can use whatever number you want)
- [X] The Outcome bar should be showing Best Bid as equal to `0.5` (for our example)

Click on the `Sell` button on the order form.

Enter the same values you entered in the previous order (if following the example, 10 quantity, .5 limit price)

Click Review and then click Confirm.

`Note: the the following approval flow will only happen the first time you attempt to trade with an account that isn't Account 1. After approving one time, assuming you don't reset the docker node, you shouldn't see approval again. This is expected.`

*Verify:*
- [X] The "Approve Augur" modal displays on the screen

Click the "Approve" button.

*Verify:*
- [X] You are prompted to sign an approval transaction

Sign the approval transaction.

*Verify:*
- [X] You are prompted to sign the order transaction immediately after signing approval.

`Note: This is the end of the approval flow, anything below should happen every trade.`

Sign the trade transaction.

After the transaction completes, we should now have a position, since this trade should result in a completely filled order from Account 1.

while still logged into Account 2...

*Verify:*
- [X] The Positions Table now has rows for each outcome
- [X] The Positions Table should show 10 shares (example value) for each outcome except for the one sold
- [X] The Position Table should show the purchase price
- [X] The charts have updated to show a new candlestick
- [X] The Order Book Chart reflects that the open order is gone and has been filled.
- [X] Login to Account 1 and verify the above, but for their side of the trade. (account 1 should only have 10 shares of the selected outcome)
- [X] The Outcome Bar shows updated % for the traded outcome, which should be `lastTradeValue * 100` (so 50% for our .5 example)

Now log back into Account 2, navigate to the market, and place an order to `Buy` for the same values you entered previously. (10 quantity at 0.5 ETH limitPrice if using the example)

*Verify:*
- [X] You didn't send any ETH with this order (outside of gas) as you should be sending your SELL shares
- [X] The Open Order bar reflects the order we just placed
- [X] The Positions Table is unchanged despite escrowing your Shares into the open order.

Switch to Account 1 (market creator account). Navigate to the market.

Execute a `Sell` order that will fill the order on the book to `Buy` placed by Account 2. (10 quantity at 0.5 ETH limit price in example)

Once the trade completes:

*Verify:*
- [X] Account 1 also didn't send any ETH (outside of gas) to place this order
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 1 Recieved `5 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~4.925 ETH` assuming 3% settlement).
- [X] Verify that the volume for this market has updated 

Login to Account 2, navigate to market page.

*Verify:*
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 2 Recieved `5 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~4.925 ETH` assuming 3% settlement).
- [X] Account 1 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph
- [X] Account 2 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph

### Scalar Market Trading

After creating a new scalar market, navigate to the markets page and find your new market's card.

click on the "trade" button on the newly created market.

When the market trading page loads, please *verfy* the following:

*Verify:*
- [X] "-" is the only outcome you can select and it's pre-selected. (if you can see the order form you have a selected outcome)
- [X] Fee % shown is the settlement Fee value set (default is 2%) at creation + the current reporting fee (hardcoded to 1% in tests)
- [X] Confirm the Expiration Date/time shown is accurate to your endtime set during market creation.
- [X] clicking on the positions title should drop down an empty postitions and open orders table.
- [X] The `LAST` price value should be equal to the midpoint for the market range (scale) since no trades have taken place.

Using Account 1 (remember, Account 1 is the account that created the market) we will now attempt to place an order.

Scalars are priced a differently from binary or categorical markets. Instead of a complete set only ever costing 1 ETH like in binary and categorical, a complete set for scalar markets costs 1 ETH per whole number of price scale. Example:

Imagine a scalar market with a min price of -50, a max price of 50, and a tickSize of 0.0001.

If you place a buy order for 1 share at 0 (the midpoint of this market) then the cost in this case would be 50 ETH. 
Buy 1 share at -25 would be 25 ETH. Buy 1 share at 25 would be 75 ETH. Buy 1 share at 50 would cost 100 ETH. Buy 1 share at -49.9999 price would cost 0.0001 ETH. However, Sell orders are the opposite, so Selling 1 share at -25 would be 75 ETH, Selling 1 at 25 would be 25 ETH, Selling 1 at 49.9999 would cost 0.0001 ETH, and Selling 1 share at -50 would cost 100 ETH.

Keeping those examples in mind, fill out the Order Form (buy or sell) on your scalar market for some quantity and some price. 

Click the Review button.

*Verify:*
- [X] quantity is accurate to what you entered
- [X] limit price is accurate to what you entered
- [X] for this trade, fee should be only for the GAS cost because we won't be closing shares here
- [X] est. cost is still accurately calculated
- [X] Confirm that Profit Loss calculations are correct. 
- [X] your ETH balance has decreased by the amount of ETH the order cost

After the transaction is successful...

*Verify:*
- [X] Outcomes table has updated to show a Bid(or Ask) Qty and Best Bid(or Ask) value, should match your order details.
- [X] The Order Book Chart should now show 1 order on the book, again confirm details.
- [X] You should see an open order row under the "Positions" section. 
- [X] The Open Order should have a positive number for quantity
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Click the Cancel button.

*Verify:*
- [X] The Open Order row should change into a purple bar
- [X] The Open Order row should say `Cancel order for N shares of "" at X ETH?` Where N is the quantity of your order and X is the price.
- [X] There should be a yes and a no button on the right side of the open order row.

click no, the ribbon should disappear and the open order row should return to what it looked like prior to clicking the Cancel button.

Click Cancel.

Click Yes.

*Verify:*
- [X] you are prompted to sign a transaction to cancel the order.

Sign the transaction to cancel the order. Once succesfully complete:

*Verify:*
- [X] the order has been removed from the open order table, and our positions/orders table is empty again.
- [X] The order has been removed from the orderbook chart
- [X] The Outcome bar is cleared of information around the order we canceled
- [X] You should have been refunded ETH that was originally taken from placing the order (minus gas).

With Account 1 still, place another BUY Order. You can use whatever values you want to test with, but for the sake of the walk through I'm going to use an example of 1 share (quantity) for 0 Limit Price (should run you 50 ETH).

After placing the order...

*Verify:*
- [X] Outcomes table has updated to show a Bid Qty and Best Bid value, should match your order details.
- [X] The Order Book Chart should now show 1 order on the BID side of the book, again confirm details.
- [X] You should see an open order row under the "Positions" section. 
- [X] The Open Order should have a positive number for quantity
- [X] The Open Order should have an average price set to the limit price of the order placed on the book.
- [X] The Open Order should have a clickable Cancel Button.

Login to Account 2. Account 2 should be an account with ETH that has never traded on Augur before.

Navigate back to the market page.

*Verify:* 
- [X] Account 1's Order is displayed accurately on the order book
- [X] The Outcome bar should be showing Bid QTY as 1 (for out example, again you can use whatever number you want)
- [X] The Outcome bar should be showing Best Bid as equal to `0`

Click on the `Sell` button on the order form.

Enter the same values you entered in the previous order (if following the example, 1 quantity, 0 limit price, again should cost 50 ETH)

Click Review and then click Confirm.

`Note: the the following approval flow will only happen the first time you attempt to trade with an account that isn't Account 1. After approving one time, assuming you don't reset the docker node, you shouldn't see approval again. This is expected.`

*Verify:*
- [X] The "Approve Augur" modal displays on the screen

Click the "Approve" button.

*Verify:*
- [X] You are prompted to sign an approval transaction

Sign the approval transaction.

*Verify:*
- [X] You are prompted to sign the order transaction immediately after signing approval.

`Note: This is the end of the approval flow, anything below should happen every trade.`

Sign the trade transaction.

After the transaction completes, we should now have a position, since this trade should result in a completely filled order from Account 1.

while still logged into Account 2...

*Verify:*
- [X] The Positions Table now has a row showing a position
- [X] The Position should have a negative number for Quantity
- [X] The Position should show the purchase price
- [X] The charts have updated to show a new candlestick
- [X] The Order Book Chart reflects that the open order is gone and has been filled.
- [X] Login to Account 1 and verify the above, but for their side of the trade.

Now log back into Account 2, navigate to the market, and place an order to `Buy` for the same values you entered previously. (1 quantity at 0 limitPrice if using the example)

*Verify:*
- [X] You didn't send any ETH with this order (outside of gas) as you should be sending your SELL shares
- [X] The Open Order bar reflects the order we just placed
- [X] The Positions bar is unchanged despite escrowing your Shares into the open order.

Switch to Account 1 (market creator account). Navigate to the market.

Execute a `Sell` order that will fill the order on the book to `Buy` placed by Account 2. (1 quantity at 0 limit price in example)

Once the trade completes:

*Verify:*
- [X] Account 1 also didn't send any ETH (outside of gas) to place this order
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 1 Recieved `50 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~49.25 ETH` assuming 3% settlement)

Login to Account 2, navigate to market page.

*Verify:*
- [X] The Position and Open Order bar are now empty again
- [X] Verify that Account 2 Recieved `50 ETH - (Settlement Fee % / 2)` (assumes example trade, answer should be `~49.25 ETH` assuming 3% settlement)
- [X] Account 1 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph
- [X] Account 2 has updated Profit Loss Data. Check: positions bar, topbar, portfolio graph


[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
