# Testing Disputing:

This section focuses on the Disputing Process. Disputing happends in rounds, each round is in a fee window. A fee window is a seven day period. Flash scripts can be used to push time to the next fee window.
  * Disputing
  * Partial bond staked
  * Whole bond staked
  * Failed dispute round
  * Multiple dispute rounds

When the user don't find any markets to dispute in a fee window they can buy participation tokens.
  * Participation 

## Disputing

- [ ] Verify accounts without REP can't dispute
- [ ] Verify market can't be disputed by using current tentative winning outcome

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
- [ ] Verify a fork is forced when a market is disputed to the point where the bond equals 275K REP

## Participation

Navigate to Reporting -> Dispute to see the PARTICIPATION button

- [ ] Verify only users with REP can buy participation tokens
- [ ] Verfiy REP balance reduces correctly after user buys participation tokens
- [ ] Verify account has participation tokens


## Notes

Make sure when pushing time to the next fee window that a fee window has been created. Fee Window get created whenever a market has been successfully reported or when there has been a successful dispute. Flash script get-balance can be used to get account balances for REP, ETH and participation tokens.