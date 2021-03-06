# Testing Disputing:

This section focuses on the Disputing Process. Disputing happens in rounds, each round is in a fee window. A fee window is a seven day period. Flash scripts can be used to push time to the next fee window.
  * Disputing
  * Partial bond staked
  * Whole bond staked
  * Failed dispute round
  * Multiple dispute rounds

When the user don't find any markets to dispute in a fee window they can buy participation tokens.
  * Participation 

## Disputing

- [x] Verify that you are shown the "No-REP" message if your account has no REP.
- [x] Verify that you cannot submit a dispute without REP.
- [x] Verify that the market's reported-on outcome is listed as the tentative winning outcome on the market card.
- [x] Verify that the market's tentative winning outcome is not listed as one of the outcomes with an associated dispute bond on the market card.
- [x] Binary: Verify these outcomes are present 'Yes', 'No', and 'Market is Invalid'
- [x] Binary: Verify there is a tentative winning outcome, and the other two have associated dispute bonds.
- [x] Categorical: Verify all market's outcomes are present, along with Market is Invalid
- [x] Categorical: Verify there is a tentative winning outcome and all others will have associated dispute bonds.
- [x] Scalar: Verify the reported-on outcome is tentative winning outcome. 
- [x] Scalar: Verify when the tentative winning outcome is Market is Invalid, no other outcomes will be listed.
- [x] Scalar: Verify when the tentative winning outcome is not Market is Invalid, Market is Invalid will have an associated dispute bond.
- [x] Scalar: Verify all successfuly dispute outcomes are listed with associated dispute bond.
- [x] Verify days remaining in dispute window is correct and increments properly, end date should be correct, and these should update when time is pushed and a new dispute window starts.
- [x] Verify that a new dispute window is created properly even when no markets were reported on or disputed in the previous dispute window.
- [x] In the first dispute round, all of the dispute bonds on a market are equal to one another.
- [x] In the first dispute round, the dispute bonds should be equal to twice the amount placed by the initial reporter. With markets reported on by the Designated Reporter, this is twice the stake placed by the Designated Reporter. With markets reported on in Open Reporting, this is twice the no-show bond. Test both.
- [x] Verify that the two numbers to the right of the progress bars are "total staked so far in dispute bond / dispute bond target".
- [x] When a market is waiting for its first Dispute Window, and while in its first Dispute window, its round number should be 1. If a dispute is successful and a market is waiting for or is in its next dispute window, its round number should be 2, etc.

### Partial bond staked

- [x] Dispute market with partial bond amount, select new outcome, stake and sign transaction.
- [x] Verify current tentative winning outcome didn't change.
- [x] Verfiy the amount of REP staked has been deducted from account balance.
- [x] Verify that you can not place negative stake, or more stake than the amount remaining in the dispute bond.
- [x] Verify that the two numbers to the right of the progress bars are "total staked so far in dispute bond / dispute bond target".
- [x] When you place stake in a dispute bond, that should be shown in an animated, light-purple bar in the dispute progress bar.
- [x] When you've placed stake in a dispute bond (and confirmed the tx), your stake placed should be shown on the market card on the Reporting: Dispute page as a light purple bar in the dispute progress bar. You should be shown a hover state with the amount you staked when you hover over that light purple bar.
- [x] Stake placed by users other than you should be displayed as a dark purple bar in the dispute progress bar.
- [x] Verify that the amount of REP you staked is reflected in "X REP Staked" (next to the dispute window end time).

### Whole bond staked

- [x] Fill a dispute bond: select an outcome, enter the full stake remaining for that dispute bond (click MAX), and sign the transaction
- [x] The market should be moved to the "Upcoming Dispute Window" section. This should happen without page refresh.
- [x] The outcome you placed stake on should be listed as the new tentative winning outcome.
- [x] The Dispute Round # should have been incremented by 1.
- [x] Verfiy the amount of REP that you staked has been deducted from your account balance.
- [x] Verify that the amount of REP you staked is reflected in "X REP Staked" (next to the dispute window end time).
- [x] (1.) Report on a new market with User1 and move time forward to bring it into its first dispute window. Switch to User2, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward so that the market goes through another dispute round with no successful disputes. Confirm that the outcome you placed stake on with User2 is the winning outcome. 
- [x] (2.) Then, confirm that you can claim the User2 stake + 50% ROI via the Claim All button on Portfolio: Reporting.
- [x] ~~[11034](https://app.clubhouse.io/augur/story/11034/incorrect-values-displayed-for-designated-reporter-for-get-reporting-fees)~~(3.) Then, confirm that User1 has no REP to claim (since they reported on a losing outcome).

### Failed dispute round

Incomplete Disputes can be redeemed for the staked REP and any share of fees collected in the fee window they placed stake in.

- [X] Move a market into Open Reporting
- [X] Purchase and sell complete sets in the market
- [X] Do an Initial Report with User 1
- [X] Move time into the dispute fee window for the market
- [X] Halfway-fill a dispute bond with User 2.
- [X] Move time to the next fee window
- [X] As User 1 confirm that you can claim the REP you staked in the unsuccessful dispute + all of the reporting fees via the Claim All button on Portfolio: Reporting.

## Multiple dispute rounds

When a dispute round completes successfully it will be available for dispute in the next fee window or else force a fork. 

- [x] Verify the disputing market can be disputed again in the next fee window
- [x] Verify the dispute bond amounts are correct. 
* Note: To verify bond amounts are correct, report on a market and then walk it through multiple dispute rounds, with varying amounts staked on different outcomes. Keep track of the amounts on each outcome as you do this. The dispute bond of an Outcome should be equal to 2x the amount staked successfully staked on all other outcomes (including stake from the initial report) minus the stake placed on that Outcome in previous rounds/reports. REP staked in unsuccessful disputes (where the REP is returned to its owner after the dispute window) does not count toward this calculation.
- [x] Verify a fork is forced when a market is disputed to the point where the successful bond equals 275K REP
- [x] (1.) Report on a new market with User1 and move time forward to bring it into its first dispute window. Switch to User2, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward to the next dispute window, switch to User1, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward so that the market goes through another dispute round with no successful disputes. Confirm that the outcome you placed stake on with User1 is the winning outcome. 
- [x] (2.) Then, confirm that you can claim the User1 stake (from reporting and disputing) + 50% ROI via the Claim All button on Portfolio: Reporting.
- [x] (3.) Then, confirm that User2 has no REP to claim (since they reported on a losing outcome).

## Participation

Navigate to Reporting -> Dispute to see the PARTICIPATION button

- [x] Verify only users with REP can buy participation tokens
- [x] Verfiy REP balance reduces correctly after user buys participation tokens
- [x] Verify that the amount of participation tokens you purchased has been added to "X REP Staked" on the Reporting: Dispute page.
- [x] Place and settle a couple trades on a market to create reporting fees. Push time forward to the next fee window. Then, verify that the Portfolio: Reporting page is showing the correct balance for REP available to claim (plus some ETH for reporting fees) and that you can claim it.
- [x] Verify that your account balance updates correctly after redeeming

## Resolved

- [x] Verify non-disputed finalized markets move to Reporting: Resolved.
- [x] Verify unsuccessful disputed finalized markets move to Reporting: Resolved.
- [x] Verify successfully disputed finalized markets move to Reporting: Resolved.
- [x] The Winning outcome should be listed on the Reporting: Resolved market card.

## Notes

Make sure when pushing time to the next fee window that a fee window has been created. Fee Windows get created whenever a market has been successfully reported or when there has been a successful dispute. Flash script get-balance can be used to get account balances for REP, ETH and participation tokens.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
