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
- [ ] Binary: Yes, No, and Market is Invalid should be listed (with one of these as the tentative winning outcome, and the other two with associated dispute bonds.
- [ ] Categorical: All of the market's outcomes, along with Market is Invalid, should be listed. One of these will be listed as the tentative winning outcome and all others will have associated dispute bonds.
- [ ] Scalar: The market's reported-on outcome will be listed as the tentative winning outcome. If the tentative winning outcome is Market is Invalid, no other outcomes will be listed. If the tentative winning outcome is not Market is Invalid, the reported-on outcome and Market is Invalid will be listed (Market is Invalid will have an associated dispute bond).
- [ ] In the first dispute round, all of the dispute bonds on a market are equal to one another.
- [ ] In the first dispute round, the dispute bonds should be equal to twice the amount placed by the initial reporter. With markets reported on by the Designated Reporter, this is twice the stake placed by the Designated Reporter. With markets reported on in Open Reporting, this is twice the no-show bond. Test both.
- [ ] When a market is waiting for its first Dispute Window, and while in its first Dispute window, its round number should be 1. If a dispute is successful and a market is waiting for or is in its next dispute window, its round number should be 2, etc.

### Partial bond staked

- [ ] Dispute market with partial bond amount, select new outcome, stake and sign transaction
- [ ] Verify current tentative winning outcome didn't change
- [ ] Verfiy the amount of REP staked has been deducted from account balance

### Whole bond staked

- [ ] Disput market with whole bond amount, select new outcome, stake remaining (click MAX) and sign transaction
- [ ] Verfiy there's a new tentative winning outcome
- [ ] Verfiy the amount of REP staked has been deducted from account balance


### Failed dispute round

When the fee window ends and the market's dispute round has not complete the stake can be reclaimed. Use flash script to push time to next fee window.

- [ ] Verify account balance is correct when user accounts relaims failed dispute bond REP
- [ ] Verify account gets participation tokens for their failed dispute bond REP 


## Multiple dispute rounds

When a dispute round completes successfully it will be available for dispute in the next fee window or else force a fork. 

- [ ] Verify the disputing market can be disputed again in the next fee window
- [ ] Verify the dispute bond grows as the dispute rounds complete successfully
- [ ] Verify a fork is forced when a market is disputed to the point where the successful bond equals 275K REP

## Participation

Navigate to Reporting -> Dispute to see the PARTICIPATION button

- [ ] Verify only users with REP can buy participation tokens
- [ ] Verfiy REP balance reduces correctly after user buys participation tokens
- [ ] Verify account has participation tokens
- [ ] Verify account can redeem REP on next fee window
- [ ] Verify account balances after redeeming

## Notes

Make sure when pushing time to the next fee window that a fee window has been created. Fee Window get created whenever a market has been successfully reported or when there has been a successful dispute. Flash script get-balance can be used to get account balances for REP, ETH and participation tokens.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
