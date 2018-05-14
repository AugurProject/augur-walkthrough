# Testing Charts
## Create market liquidity charts

### Categorical Market
Start creating a categorical market with at least three outcomes. Then, when you get to the liquidity page:

*Verify:*
- [ ] You are on the liquidity page
- [ ] The 'create order' form is shown
- [ ] Outcome dropdown is on the default state, and shows your outcomes when opened.
- [ ] Charts display "No open Orders"
- [ ] Depth Chart Precision +/- symbols are not visible.

Add buy order for 1st outcome with qty 0.1 and limit price 0.1

- [ ] The market mid-point is set to 0.1 in both depth and order chart
- [ ] The order shows up in the order book
- [ ] Hover over order manifests depth chart lines accordingly

Add a second buy order for 1st outcome with qty 0.2 and limit price 0.2

- [ ] The new order is shown at the top of the buy order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.2 in both depth and order chart

Add a sell order for 1st outcome with qty 0.3 and limit price 0.3

- [ ] The new order is shown at the bottom of the sell order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.25 in both depth and order chart
- [ ] Clicking on an order in the order book does not auto-fill the order form
- [ ] Hit the "Next: Review" button, then hit "Previous: Liquidity". The orders you entered should still be listed in the depth chart/order book.

Select second outcome in the order form

- [ ] Charts again display "No open Orders"
- [ ] Order form should be empty

### Binary Market
Start creating a binary market. Then, when you get to the liquidity page:

*Verify:*
- [ ] The 'create order' form is shown
- [ ] There are no outcomes to select from.
- [ ] Charts display "No open Orders"
- [ ] Depth Chart Precision +/- symbols are not visible.

Add buy order with qty 0.1 and limit price 0.1

- [ ] The market mid-point is set to 0.1 in both depth and order chart
- [ ] The order shows up in the order book
- [ ] Hover over order manifests depth chart lines accordingly

Add a second buy order with qty 0.2 and limit price 0.2

- [ ] The new order is shown at the top of the buy order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.2 in both depth and order chart

Add a sell order with qty 0.3 and limit price 0.3

- [ ] The new order is shown at the bottom of the sell order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.25 in both depth and order chart
- [ ] Clicking on an order in the order book does not auto-fill the order form
- [ ] Hit the "Next: Review" button, then hit "Previous: Liquidity". The orders you entered should still be listed in the depth chart/order book.

### Scalar Market
Start creating a scalar market. Then, when you get to the liquidity page:

*Verify:*
- [ ] The 'create order' form is shown
- [ ] There are no outcomes to select from.
- [ ] Charts display "No open Orders"
- [ ] Depth Chart Precision +/- symbols are not visible.

Add buy order with qty 0.1 and limit price 0.1

- [ ] The market mid-point is set to 0.1 in both depth and order chart
- [ ] The order shows up in the order book
- [ ] Hover over order manifests depth chart lines accordingly

Add a second buy order with qty 0.2 and limit price 0.2

- [ ] The new order is shown at the top of the buy order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.2 in both depth and order chart

Add a sell order with qty 0.3 and limit price 0.3

- [ ] The new order is shown at the bottom of the sell order listing
- [ ] The axis labels are visible and readable
- [ ] The market mid-point is set to 0.25 in both depth and order chart
- [ ] Clicking on an order in the order book does not auto-fill the order form
- [ ] Hit the "Next: Review" button, then hit "Previous: Liquidity". The orders you entered should still be listed in the depth chart/order book.


## Trading
*Verify:*
- [ ] Mid line is actually in the middle
- [ ] +/- fixed precision buttons work
- [ ] + is limited to max 8 digits
- [ ] - is limited to min 0 digits
- [ ] Verify precision change affects all numbers visible (Including values shown on hover)
- [ ] Hovering over the midline displays the same value in all three charts
- [ ] There should be no PropType errors in console

### Depth Chart
#### Setup
Several of the pre-populated markets have a few ask/sell orders in place.

*Verify:*
Hovering over chart notice the following
- [ ] Depth headers updates (bid price, qty, depth)
- [ ] Vertical line "clamps" to depth of chart
- [ ] Horizontal value is shown on candlestick chart

### Order Book
#### Setup
Several of the pre-populated markets have a few ask/sell orders in place.

*Verify:*
- [ ] Clicking buy order populates trade form
- [ ] Clicking sell order populates trade form
- [ ] By price the largest "Ask" order should be sorted toward the center line
- [ ] By Price the smallest "Buy" order should be sorted toward the center line
- [ ] Hovering over an order causes the depth chart to react as if it were hovered inside the depth chart

#### Further action:
Submit 'BUY 'orders until scrollbars appear

*Verify:*
- [ ] Formatting stays consistent
- [ ] Order listing becomes scrollable when appropriate

#### Further action:
1. Scroll to the tail end of one side of the order book
2. Add one more 'BUY' order

*Verify:*
- [ ] The highlighted order has scrolled back into view

#### Further action:
Submit 'SELL' orders until scrollbars appear

*Verify:*
- [ ] Formatting stays consistent
- [ ] Order listing becomes scrollable when appropriate

#### Further action:
1. Scroll to the top of ask orders (highlighted order should no longer be visible)
2. Add one more 'SELL' order

*Verify:*
- [ ] The highlighted order has scrolled back into view

### CandleStick Chart
#### Setup
NOTE: Be sure to use a privacy window for all of this. It would appear metamask prevents fake block time from propogating to the client.
1. Start local docker compose env in augur repo `npm run docker:spin-up`
2. Create a new market
2. For convenience the script below is provided in augur UI repo. Located at `augur/scripts/pop-candlesticks.sh`. It will populate candlestick chart with fake data. [augur](https://github.com/AugurProject/augur) (Be sure to pass in the market ID create in step 2)
3. Navigate to relevent trade page and select relevant outcome. The script goes to work on outcome 1, you may need to click around a bit.

*Verify:*
- [ ] Per period Volume bars are appearing at the bottom of the chart
- [ ] Candlesticks are populating correctly

Hovering over a candlestick will....
- [ ] Populate the candlestick header
- [ ] Highlight the order in the depth chart

#### Further action:
Select various period/range combinations

*Verify:*
- [ ] Time scale changes in chart
- [ ] If period/range is invalid "NO COMPLETE TRADES" is shown


