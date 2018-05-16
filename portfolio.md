# Testing Portfolio:

This section focuses on the Portfolio sections. Portfolio is mostly reviewing results of user actions. These are the portfolio sections:

  * Positions
  * My Markets
  * Favorites
  * Transactions
  * Reporting


## Positions

Positions includes trade positions, open orders and profit/loss. Trades will need to be made to produce positions and open orders.

- [X] Verify that the null state is shown if user doesn't have any positions or open orders.
- [X] Verify correct market card is listed on Positions page when position and/or open orders is created.
- [X] End date on market card should be listed in current user's timezone (UTC+/-#)
- [X] Binary: Create a new order. Verify that the stats accompanying the order are correct.
- [X] Categorical: Create a new order. Verify that the stats accompanying the order are correct.
- [X] Scalar: Create a new order. Verify that the stats accompanying the order are correct.
- [X] Binary: Create a new position. Verify that the stats accompanying the order are correct.
- [X] Categorical: Create a new position. Verify that the stats accompanying the order are correct.
- [X] Scalar: Create a new position. Verify that the stats accompanying the order are correct.
- [X] Verify "My Positions" and "Open Orders" can be toggled open and closed.
- [X] Verify that all "My Positions" start open when the page is loaded.
- [X] Verify the market's total realized, unrealized and total profit/loss update correctly when a position is created.
- [X] Verify the market's total realized, unrealized and total profit/loss update correctly when a position is closed.
- [X] Verify the market's total realized, unrealized and total profit/loss update correctly when an order is added to a position.
- [X] Verify position can be closed by clicking "Close".
- [X] Verify open order can be canceled by clicking "Cancel".
- [X] Verify account balance updates correctly when position is closed.
- [X] Verify account balance updates correctly when open order is canceled.
- [X] Verify profit/loss chart in header displays correct information based on user trading activity (talk to Paul about what this should display)
- [X] Verify markets are moved to "In Reporting" on the Portfolio page when that phase starts.
- [X] Verify markets are moved to "Resolved" on the Portfolio page when Reporting & Disputing is over.
- [X] Verify the user can finalize the market from the Portfolio page if it has not been finalized already.
- [X] Report on a market, move time forward so the market resolves, then collect your stake. Verify that collecting your stake finalizes the market, and that the "Calculate Proceeds"/finalize button is no longer shown on the Portfolio page. The three day waiting period should show instead.
- [X] Verify user can't claim their unrealized profits during 3 day waiting period.
- [X] Verify user can claim their unrealized profits when the market is finalized and waiting period is over.
- [X] (INVESTIGATING POSSIBLE FAILURE) Verify that the claimed proceeds are now listed as realized profits on the position.
- [X] (INVESTIGATING POSSIBLE FAILURE) Verify that the market card's total unrealized/realized profits updates correctly.
- [X] Verify that "Export Data" (in the top right of the header) works.

## My Markets

My markets is strictly for markets created by the user account.

- [x] Verify this view is empty if user hasn't create any markets.
- [x] Verify all user account created market show in this section.
- [x] Verify that markets move through "Open", "In Reporting", and "Resolved" sections appropriately.
- [x] Verify the market's volume updates correctly when trades occur.
- [ ] Verify that outstanding returns become available to the market creator when complete sets settle, and that the amount that becomes available is correct.
- [ ] Verify that those outstanding returns from settled trades can be collected and the Collected Returns balance on the market updates correctly.
- [ ] Verify that, when a market is resolved to something other than "Market is Invalid" (and the reporter claims their REP which triggers market finalization), the Validity bond becomes available in "Outstanding Returns", is claimable, and the Collected Returns balance updates properly.
- [x] Verify that, when a market is reported on by the Designated Reporter, the reporter gas bond becomes available in "Outstanding Returns", is claimable, and the Collected Returns balance updates properly.
- [ ] Verify that most recently resolved markets appear at the top of the Resolved list.

## Favorites

- [x] Verify view is blank if user hasn't marked any markets as favorite.
- [x] Verify only markets marked as favorite show up.
- [x] Verify that unfavorited markets are removed from the view.
- [x] Verify pagination works.

## Transactions

- [ ] Verify view shows a null state if user hasn't created any transactions.
- [ ] Verify create market transaction is shown when a market is successfully created and that details are accurate.
- [ ] Verify that transfer transactions are shown when ETH is successfully transferred and that details are accurate.
- [ ] Verify that transfer transactions are shown then REP is successfully transferred and that details are accurate.
- [ ] Verify that trade transactions are shown when the user makes successful trade and that details are accurate.
- [ ] Verify all sub trades are included as linked trades in trade transactions.
- [ ] Verify open order transactions get created when user creates open orders.
- [ ] Verify that the date on the transaction is correct.
- [ ] Verify that the most recent transactions are listed first.
- [ ] Verify that range dropdown filters correctly.

## Reporting

Currently this section is for claiming ETH/REP reporting fees from fee window participation tokens, initial reports/dispute crowdsourcers of non-forked markets. If a forked market exists and the user has claimable ETH/REP in it, a Forked Market card will be displayed under the Claim button for non-forked markets, and the user should be able to click the Claim button to migrate those fees to the corresponding child universe.

#### Settlement Fees
Use multiple users to create positions on a market and have open orders so those positions can be closed. For example, on a binary market use three users:
* User1 creates buy open order for 100 shares at .1
* User2 takes that order
* User1 creates sell open order for 100 shares at .5
* User2 closes position therefore taking that order

#### Getting REP
For resporters to get their REP the market has to be in awaiting finalization or finalized. Reporters get a portion of the settlement fees on the fee window they report in.


### Participation Tokens

- [x] Verify user can claim correct amount of paricipation tokens on one fee window
- [x] Verify user can claim the correct amount of participation tokens when they have participation tokens across multiple fee windows

### Designated Reporters

- [x] Verify designated reporter can claim correct amount of REP on successfully reported outcome.
- [x] Verify designated reporter gets portion of trading fees in ETH
- [x] Verify designated reporter can reclaim correct amount of REP on multiple finalized markets where their outcome won
- [x] Verify designated reporter can't reclaim REP on any finalized markets where their outcome lost

### Initial Reporters (i.e. reporters other than the designated reporter)

- [ ] Verify initial reporter can claim correct amount of REP for reporting in fee window
- [ ] Verify initial reporter can claim correct amount of ETH from tradding fees for reporting in fee window
- [ ] Verify initial reporter can reclaim REP on finalized markets where their outcome won
- [ ] Verify initial reporter can't reclaim REP on finalized markets where their outcome lost

### Dispute Contributor

- [ ] Verify contributor can claim correct amount of REP from finalized markets that resolve on same outcome as their successful dispute rounds
- [ ] Verify contributor can reclaim amount of REP originally staked on dispute bonds that didn't make crowdsourcing goal
- [ ] Verify contributor can't claim REP from finalized markets that resolve on different outcome as their successful dispute rounds

### Forked Market Initial Reporter/Dispute Contributor

- [ ] Verify that if user is a designated reporter or inital reporter, they can migrate their REP to the correct child universe of the forked market
- [ ] Verify that if user contributed to a dispute crowdsourcer of a forked market, they can migrate their REP to the correct child universe


[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
