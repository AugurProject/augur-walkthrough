# Testing Portfolio:

This section focuses on the Portfolio sections. Portfolio is mostly reviewing results of user actions. These are the portfolio sections:

  * Positions
  * My Markets
  * Favorites
  * Transactions
  * Reporting


## Positions

Positions includes trade positions, open orders and profit/loss. Trades will need to be made to produce positions and open orders.

- [X] (FAILED) Verify that the null state is shown if user doesn't have any positions or open orders.
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
- [X] (FAILED) Verify the market's total realized, unrealized and total profit/loss update correctly when a position is created.
- [X] (FAILED) Verify the market's total realized, unrealized and total profit/loss update correctly when a position is closed.
- [X] (FAILED) Verify the market's total realized, unrealized and total profit/loss update correctly when an order is added to a position.
- [X] Verify position can be closed by clicking "Close".
- [X] Verify open order can be canceled by clicking "Cancel".
- [X] Verify account balance updates correctly when position is closed.
- [X] Verify account balance updates correctly when open order is canceled.
- [X] (FAILED) Verify profit/loss chart in header displays correct information based on user trading activity (talk to Paul about what this should display)
- [X] Verify markets are moved to "In Reporting" on the Portfolio page when that phase starts.
- [X] Verify markets are moved to "Resolved" on the Portfolio page when Reporting & Disputing is over.
- [X] (FAILED) Verify the user can finalize the market from the Portfolio page if it has not been finalized already.
- [X] (FAILED) Report on a market, move time forward so the market resolves, then collect your stake. Verify that collecting your stake finalizes the market, and that the "Calculate Proceeds"/finalize button is no longer shown on the Portfolio page. The three day waiting period should show instead.
- [X] Verify user can't claim their unrealized profits during 3 day waiting period.
- [X] (FAILED) Verify user can claim their unrealized profits when the market is finalized and waiting period is over.
- [ ] Verify that the claimed proceeds are now listed as realized profits on the position.
- [ ] Verify that the market card's total unrealized/realized profits updates correctly.
- [ ] Verify that "Export Data" (in the top right of the header) works.

## My Markets

My markets is strictly for markets created by the user account.

- [ ] Verify this view is empty if user hasn't create any markets.
- [ ] Verify all user account created market show in this section.
- [ ] Verify that markets move through "Open", "In Reporting", and "Resolved" sections appropriately.
- [ ] Verify the market's volume updates correctly when trades occur.
- [ ] Verify that outstanding returns become available to the market creator when complete sets settle, and that the amount that becomes available is correct.
- [ ] Verify that those outstanding returns from settled trades can be collected and the Collected Returns balance on the market updates correctly.
- [ ] Verify that, when a market is resolved to something other than "Market is Invalid" (and the reporter claims their REP which triggers market finalization), the Validity bond becomes available in "Outstanding Returns", is claimable, and the Collected Returns balance updates properly.
- [ ] Verify that, when a market is reported on by the Designated Reporter, the reporter gas bond becomes available in "Outstanding Returns", is claimable, and the Collected Returns balance updates properly.
- [ ] Verify that most recently resolved markets appear at the top of the Resolved list.

## Favorites

- [ ] Verify view is blank if user hasn't marked any markets as favorite.
- [ ] Verify only markets marked as favorite show up.
- [ ] Verify that unfavorited markets are removed from the view.
- [ ] Verify pagination works.

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

Currently this section is for claiming ETH/REP from market trading fees, market creation bonds, open reporting no-show REP bonds, REP from successful disputes and ETH from reporting fees from participation tokens 

### Market Creator

- [ ] Verify market creator can claim settlement fees based on market settlement percentage
- [ ] Verify market creator can reclaim no-show bond when designate reporter reports
- [ ] Verify market creator can't reclaim no-show bond when designate reporter doesn't reporter
- [ ] Verify market creator can reclaim reporter gas bond when designated reporter reports
- [ ] Verify market creator can't reclaim reporter gas bond when designate reporter doesn't repoert
- [ ] Verify market creator can reclaim validity bond when their market resolves not invalid
- [ ] Verify market creator can't reclaim validity bond when their market resolves as invalid

### Open Reporters

- [ ] Verify open reporter can claim no-show bond in REP
- [ ] Verify open reporter can claim reporter gas bond in ETH
- [ ] Verify open reporter can claim settlement fees for reporting in fee window
- [ ] Verify open reporter can reclaim REP on finalized markets where their outcome won
- [ ] Verify open reporter can't reclaim REP on finalized markets where their outcome lost

### Designate Reporters

- [ ] Verify designate reporter can claim settlement fees for reporting in fee window
- [ ] Verify designate reporter can reclaim REP on finalized markets where their outcome won
- [ ] Verify designate reporter can't reclaim REP on finalized markets where their outcome lost

### Dispute Contributor

- [ ] Verify contributor can claim settlement fees for contributing to successful dispute in fee window
- [ ] Verify contributor can claim settlement fees for contributing to not successful dispute in fee window
- [ ] Verify contributor can claim REP from finalized markets that resolve on same outcome as their successful dispute rounds
- [ ] Verify contributor can reclaim REP on dispute bonds that didn't make
- [ ] Verify contributor can't claim REP from finalized markets that resolve on different outcome as their successful dispute rounds



[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
