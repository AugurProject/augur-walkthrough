# Testing Charts
## Create market liquidity charts
### Categorical Market
#### Steps
1. Click create market
2. Enter Market question/tags, etc. 
3. Click 'NEXT'
4. Select 'Multiple Choice' option
5. Add at least 3 potential outcomes
6. Click 'NEXT'
7. Fill out next page with valid info
8. Click 'NEXT'

*Verify:*
- [ ] You are on the liquidity page
- [ ] Buy 'create order' form is shown]
- [ ] Outcome dropdown is empty
- [ ] Charts display "No open Orders"
- [ ] Depth Chart Precision +/- symbols are not visible.

#### Further action:
Add buy order for 1st outcome with qty 0.1 and limit price 0.1

*Verify:*
- [ ] The market mid-point is set to in both depth and order chart to 0.1
- [ ] The order shows up in the order book
- [ ] Hover over order manifests depth chart lines accordingly

#### Further action:
Add a second buy order for 1st outcome with qty 0.2 and limit price 0.2

*Verify:*
- [ ] The new order is shown at the top of the buy order listing
- [ ] The axis labels are visible and readable
- [ ] @TODO What should happen to midpoint line

#### Further action:
Add a sell order for 1st outcome with qty 0.3 and limit price 0.3

*Verify:*
- [ ] @TODO Should form reset on tab change?

#### Further action:
Select second outcome on form

*Verify:*
- [ ] Charts again display "No open Orders"
- [ ] @TODO Should form reset?
- [ ] @TODO Should order book click populate form?


## Trading
*Verify:*
- [ ] Mid line is actually in the middle
- [ ] +/- fixed precision buttons work
- [ ] + is limited to max 8 digits
- [ ] - is limited to min 0 digits
- [ ] Verify precision change affects all numbers visible (Including values shown on hover)
- [ ] Hovering over the midline displays the same value in all three charts
- [ ] Check PropType errors in console

### Depth Chart
#### Setup
Several of the pre-populated markets have a few ask/sell orders in place.

*Verify:*
Hovering over chart notice the following
- [ ] Depth header updates
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
2. Populate candlestick chart with fake data by running the following script inside your [augur.js](https://github.com/AugurProject/augur.js) (Be sure to pass in the market ID create in step 2)
3. Navigate to relevent trade page and select relevant outcome. The script goes to work on outcome 1, you may need to click around a bit.

```bash
#!/usr/bin/env bash

if [ $# -eq 0 ]
  then
    echo "Please supply a valid market ID.";
    exit 1;
fi

MARKET_ID=$1
OUTCOME=1

# Data in form of:
# open	high	low	close	volume
# This data is a normalized version of the microsoft stock daily time series
curl https://gist.githubusercontent.com/justinbarry/bf6cd9afcd8778027e211105562b89d7/raw/cae40936cc1930e310411ec27d957769b93d8068/data.tsv | \
while IFS=$'\t' read -r -a dataArray
do
  for j in "${dataArray[@]}"
  do
    echo "Sell trade $j";
    ETHEREUM_PRIVATE_KEY=fae42052f82bed612a724fec3632f325f377120592c75bb78adfcceae6470c5a node scripts/flash create-market-order --marketId $MARKET_ID --outcome $OUTCOME --orderType sell --shares "$(jot  -p 4 -r 1 0 1)" --price "$j"

    echo "Filling trade $j";
    ETHEREUM_PRIVATE_KEY=48c5da6dff330a9829d843ea90c2629e8134635a294c7e62ad4466eb2ae03712 node scripts/flash fill-market-orders -m $MARKET_ID -o $OUTCOME -t buy;

    node scripts/flash push-timestamp -s -c 600;
  done

  echo "Push time";
  node scripts/flash push-timestamp -s -c 3600;
done
```

*Verify:*
- [ ] Per period Volume bars are appearing at the bottom of the chart

Hovering over a candlestick will....
- [ ] Populate the candlestick header
- [ ] Highlight the order in the depth chart

#### Further action:
Select various period/range combinations

*Verify:*
- [ ] Time scale changes in chart
- [ ] If period/range is invalid "NO COMPLETE TRADES" is shown


