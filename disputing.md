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

- [ ] Verify that you are shown the "No-REP" message if your account has no REP.
- [ ] Verify that you cannot submit a dispute without REP.
- [ ] Verify that the market's reported-on outcome is listed as the tentative winning outcome on the market card.
- [ ] Verify that the market's tentative winning outcome is not listed as one of the outcomes with an associated dispute bond on the market card.
- [ ] Binary: Verify these outcomes are present 'Yes', 'No', and 'Market is Invalid'
- [ ] Binary: Verify there is a tentative winning outcome, and the other two have associated dispute bonds.
- [ ] Categorical: Verify all market's outcomes are present, along with Market is Invalid
- [ ] Categorical: Verify there is a tentative winning outcome and all others will have associated dispute bonds.
- [ ] Scalar: Verify the reported-on outcome is tentative winning outcome. 
- [ ] Scalar: Verify when the tentative winning outcome is Market is Invalid, no other outcomes will be listed.
- [ ] Scalar: Verify when the tentative winning outcome is not Market is Invalid, Market is Invalid will have an associated dispute bond.
- [ ] Scalar: Verify all successfuly dispute outcomes are listed with associated dispute bond.
- [ ] Verify days remaining in dispute window is correct and increments properly, end date should be correct, and these should update when time is pushed and a new dispute window starts.
- [ ] Verify that a new dispute window is created properly even when no markets were reported on or disputed in the previous dispute window.
- [ ] In the first dispute round, all of the dispute bonds on a market are equal to one another.
- [ ] In the first dispute round, the dispute bonds should be equal to twice the amount placed by the initial reporter. With markets reported on by the Designated Reporter, this is twice the stake placed by the Designated Reporter. With markets reported on in Open Reporting, this is twice the no-show bond. Test both.
- [ ] Verify that the two numbers to the right of the progress bars are "total staked so far in dispute bond / dispute bond target".
- [ ] When a market is waiting for its first Dispute Window, and while in its first Dispute window, its round number should be 1. If a dispute is successful and a market is waiting for or is in its next dispute window, its round number should be 2, etc.

### Partial bond staked

- [ ] Dispute market with partial bond amount, select new outcome, stake and sign transaction.
- [ ] Verify current tentative winning outcome didn't change.
- [ ] Verfiy the amount of REP staked has been deducted from account balance.
- [ ] Verify that you can not place negative stake, or more stake than the amount remaining in the dispute bond.
- [ ] Verify that the two numbers to the right of the progress bars are "total staked so far in dispute bond / dispute bond target".
- [ ] When you place stake in a dispute bond, that should be shown in an animated, light-purple bar in the dispute progress bar.
- [ ] When you've placed stake in a dispute bond (and confirmed the tx), your stake placed should be shown on the market card on the Reporting: Dispute page as a light purple bar in the dispute progress bar. You should be shown a hover state with the amount you staked when you hover over that light purple bar.
- [ ] Stake placed by users other than you should be displayed as a dark purple bar in the dispute progress bar.
- [ ] Verify that the amount of REP you staked is reflected in "X REP Staked" (next to the dispute window end time).

### Whole bond staked

- [ ] Fill a dispute bond: select an outcome, enter the full stake remaining for that dispute bond (click MAX), and sign the transaction
- [ ] The market should be moved to the "Upcoming Dispute Window" section. This should happen without page refresh.
- [ ] The outcome you placed stake on should be listed as the new tentative winning outcome.
- [ ] The Dispute Round # should have been incremented by 1.
- [ ] Verfiy the amount of REP that you staked has been deducted from your account balance.
- [ ] Verify that the amount of REP you staked is reflected in "X REP Staked" (next to the dispute window end time).
- [ ] (1.) Report on a new market with User1 and move time forward to bring it into its first dispute window. Switch to User2, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward so that the market goes through another dispute round with no successful disputes. Confirm that the outcome you placed stake on with User2 is the winning outcome. 
- [ ] (2.) Then, confirm that you can claim the User2 stake + 50% ROI via the Claim All button on Portfolio: Reporting.
- [ ] (3.) Then, confirm that User1 has no REP to claim (since they reported on a losing outcome).

### Failed dispute round

If Outcome1's dispute bond is not filled by the time Outcome2's dispute bond is successfully filled or the dispute window ends, then stake placed on Outcome1's dispute bond can be reclaimed.

- [ ] Report on a new market with User1 and move time forward to bring it into its first dispute window. Halfway-fill an outcome's dispute bond. Place and settle a couple trades on a market to creat reporting fees. Push time forward to the next dispute window. Then, confirm that you can claim the REP you staked in the unsuccessful dispute + a share of the reporting fees from the previous fee window via the Claim All button on Portfolio: Reporting.
- [ ] (1.) Report on a new market with User1 and move time forward to bring it into its first dispute window. Halfway-fill Outcome1's dispute bond. Switch to User2, and completely fill Outcome2's dispute bond so Outcome2 becomes the new tentative winning outcome and the market is moved to the Upcoming Dispute Window. Place and settle a couple trades on a market to creat reporting fees.
- [ ] (2.) Confirm that nothing is available to claim for either user via the Portfolio: Reporting page (nothing should be available because the dispute window hasn't ended.
- [ ] (3.) Push time forward to the next dispute window. Then, switch to User1 and confirm that you can claim the REP you staked in the unsuccessful dispute + a share of the reporting fees from the previous fee window via the Claim All button on Portfolio: Reporting.

## Multiple dispute rounds

When a dispute round completes successfully it will be available for dispute in the next fee window or else force a fork. 

- [ ] Verify the disputing market can be disputed again in the next fee window
- [ ] Verify the dispute bond amounts are correct. 
* Note: To verify bond amouts are correct, report on a market and then walk it through multiple dispute rounds, with varying amounts staked on different outcomes. Keep track of the amounts on each outcome as you do this. The dispute bond of Outcome should be equal to 2x the amount staked successfully staked on all other outcomes (including stake from the initial report) minus the stake placed on Outcome in previous rounds/reports. REP staked in unsuccessful disputes (where the REP is returned to its owner after the dispute window) does not count toward this calculation.
- [ ] Verify a fork is forced when a market is disputed to the point where the successful bond equals 275K REP
- [ ] (1.) Report on a new market with User1 and move time forward to bring it into its first dispute window. Switch to User2, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward to the next dispute window, switch to User1, and fill an outcome's dispute bond so that outcome becomes the new winning outcome. Push time forward so that the market goes through another dispute round with no successful disputes. Confirm that the outcome you placed stake on with User1 is the winning outcome. 
- [ ] (2.) Then, confirm that you can claim the User1 stake (from reporting and disputing) + 50% ROI via the Claim All button on Portfolio: Reporting.
- [ ] (3.) Then, confirm that User2 has no REP to claim (since they reported on a losing outcome).

## Participation

Navigate to Reporting -> Dispute to see the PARTICIPATION button

- [ ] Verify only users with REP can buy participation tokens
- [ ] Verfiy REP balance reduces correctly after user buys participation tokens
- [ ] Verify that the amount of participation tokens you purchased has been added to "X REP Staked" on the Reporting: Dispute page.
- [ ] Place and settle a couple trades on a market to create reporting fees. Push time forward to the next fee window. Then, verify that the Portfolio: Reporting page is showing the correct balance for REP available to claim (plus some ETH for reporting fees) and that you can claim it.
- [ ] Verify that your account balance updates correctly after redeeming

## Resolved

- [ ] Verify non-disputed finalized markets move to Reporting: Resolved.
- [ ] Verify unsuccessful disputed finalized markets move to Reporting: Resolved.
- [ ] Verify successfully disputed finalized markets move to Reporting: Resolved.
- [ ] The Winning outcome should be listed on the Reporting: Resolved market card.

## Notes

Make sure when pushing time to the next fee window that a fee window has been created. Fee Windows get created whenever a market has been successfully reported or when there has been a successful dispute. Flash script get-balance can be used to get account balances for REP, ETH and participation tokens.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
