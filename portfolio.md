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

- [x] Verify view shows a null state if user hasn't created any transactions.
- [ ] [10970](https://app.clubhouse.io/augur/story/10970/market-created-in-transactions-date-is-wrong) Verify create market transaction is shown when a market is successfully created and that details are accurate.
- [ ] [10967](https://app.clubhouse.io/augur/story/10967/eth-and-rep-transfers-don-t-show-up-in-transactions) Verify that transfer transactions are shown when ETH is successfully transferred and that details are accurate.
- [ ] [10967](https://app.clubhouse.io/augur/story/10967/eth-and-rep-transfers-don-t-show-up-in-transactions) Verify that transfer transactions are shown then REP is successfully transferred and that details are accurate.
- [x] Verify that trade transactions are shown when the user makes successful trade and that details are accurate.
- [x] Verify all sub trades are included as linked trades in trade transactions.
- [x] Verify open order transactions get created when user creates open orders.
- [ ] [10970](https://app.clubhouse.io/augur/story/10970/market-created-in-transactions-date-is-wrong) Verify that the date on the transaction is correct.
- [x] Verify that the most recent transactions are listed first.
- [ ] [10972](https://app.clubhouse.io/augur/story/10972/range-dropdown-not-filtering-correctly-for-transactions) Verify that range dropdown filters correctly.

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
- [X] Verify user has claim button disabled when there is nothing to claim

### Designated Reporters

- [x] Verify designated reporter can claim correct amount of REP on successfully reported outcome.
- [x] Verify designated reporter gets portion of trading fees in ETH
- [x] Verify designated reporter can reclaim correct amount of REP on multiple finalized markets where their outcome won
- [x] Verify designated reporter can't reclaim REP on any finalized markets where their outcome lost

### Initial Reporters (i.e. reporters other than the designated reporter)

- [ ] [10832](https://app.clubhouse.io/augur/story/10832/unclaimedrepearned-has-balance-getreportingfee-when-it-should-be-0) Verify initial reporter can claim correct amount of REP for reporting in fee window
- [ ] [10842](https://app.clubhouse.io/augur/story/10842/unclaimedeth-has-incorrect-balance-for-initial-reporter-when-there-was-no-dispute)Verify initial reporter can claim correct amount of ETH from trading fees for reporting in fee window
- [x] Verify initial reporter can reclaim REP on finalized markets where their outcome won
- [x] Verify initial reporter can't reclaim REP on finalized markets where their outcome lost
- [x] Verify initial reporter can claim ETH from trading fees when reporting on failed outcome

### Dispute Contributor

Using Account1 & Account2, do the following on a market:

1. Make sure both accounts have lots of REP.
2. Use Account1 to stake 0.3497 REP an initial report for outcome 0.
3. Push time to reach Crowdsourcing Dispute phase.
4. Use Account2 to dispute by staking max (0.6994 REP) on outcome 1.
5. Push time to go to next fee window.
6. Use Account1 to dispute by staking max (1.0491 REP) on outcome 0.
7. Push time to go to next fee window.
8. Use Account2 to dispute by staking some amount less than the max (1.9 REP) on outcome 1.
9. Push time until market state is AWAITING_FINALIZATION.
10. Finalize the market.

- [x] Verify that Account1 can claim: 1.5x the amount of REP originally staked on the initial report & crowdsourcer for outcome 0; ETH fees for staking REP on the intial report & crowdsourcer for outcome 0.
- [ ] [10851](https://app.clubhouse.io/augur/story/10851/getreportingfees-not-returning-unclaimedeth-as-expected)Verify that Account2 can claim: the amount of REP staked on the crowdsourcer for outcome 1 (when it didn't reach its goal); ETH fees for staking on the crodwsourcer for outcome 1 twice.
- [ ] [10843](https://app.clubhouse.io/augur/story/10843/unmade-unfilled-dispute-bonds-can-t-be-reclaimed-by-disputer)Verify that Account2 cannot claim REP staked on crowdsourcer for outcome 1 in the rounds where the max was reached for that crowdsourcer.

### Forked Market Initial Reporter/Dispute Contributor

- [x] Verify that if user is a designated reporter or inital reporter, they can migrate their REP to the correct child universe of the forked market
- [x] Verify that if user contributed to a dispute crowdsourcer of a forked market, they can migrate their REP to the correct child universe
- [ ] [10864](https://app.clubhouse.io/augur/story/10864/getreportingfees-returns-unclaimedforkfees-after-rep-is-migrated)Verify that, after migrating unclaimed fork REP to the child universe, the Forked Market card no longer displays on the Portfolio: Reporting page

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
