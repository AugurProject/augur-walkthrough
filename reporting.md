# Testing Reporting:

This section focuses on the Initial Reporting Process.

In order for an initial report to occur the market's end time has to elapse. Flash scripts can be used to set timestamp within designated reporting or open reporting. The designated reporting timeframe is a 3 day window starting 1 second after market end time. Open reporting timeframe starts 1 second after designate reporting ends and doesn't have an end time.

## Designated Reporting

Navigate to Reporting -> Reporting to see the markets in designated reporting state. 

- [ ] Verify that a market shows up in the Designated Reporting section one second after its end date has passed.
- [ ] Create a market where the market creator is the designated reporter and then move time forward so the market is in the DR stage. Verify that only the market creator can see the market listed under Designated Reporting, and verify that only the market creator can report on the market.
- [ ] Create a market where the someone other than the market creator is the designated reporter. Then, move time forward so the market is in the DR stage. Verify that only the designated reporter can see the market listed under Designated Reporting, and verify that only the designated reporter can report on the market.
- [ ] Verify market creator gets their no-show REP bond when non market creator designated reporter reports
- [ ] Verify market creator gets their initial reporter gas bond when non market creator designated reporter reports
- [ ] Verify that the end date shown on the market card is correct.
- [ ] Verify that the reporting end date shown on the market card is correct.
- [ ] Verify that the pie chart showing time elapsed is correct (try this with a couple different times).
- [ ] Binary market: Report on market by selecting an outcome and signing the transaction.
- [ ] Categorical market: Report on market by selecting an outcome and signing the transaction.
- [ ] Scalar market: Report on market by entering an outcome and signing the transaction.
- [ ] Scalar market: Verify that you cannot enter an outcome below the min or above the max.
- [ ] Verify REP balance was deducted (If market creator and desigate reporter accounts are the same there's no balance change)
- [ ] The market should be removed from the Reporting: Markets page and move to the Reporting: Dispute page. It should be listed under "Upcoming Dispute Window". This should happen without page refresh.
- [ ] Move time forward so the dispute window begins. The "X Stake Placed" should reflect the amount of stake you placed in the report.
- [ ] Verify the tentative winning outcome shown on the market card on the Reporting: Dispute page is correct.
- [ ] While the market is in the dispute window, settle a couple trades on another market so some reporting fees are generated. Then, push time forward to end the dispute windoow (without disputing the tenative winning outcome on your market) so your market resolves. Verify that you can collect your staked REP and portion of ETH fees on the Portfolio: Reporting page. The balance should be shown, and you should be able to claim that balance with the Claim All button.

## Open Reporting

Navigate to Reporting -> Reporting to see the markets in open reporting state.

- [ ] Verify that a market moves into Open Reporting when the 3-day DR window is up. This should happen without page refresh.
- [x] Verify that anyone can report on a market in Open Reporting. Try this with an account other than the market creator and designated reporter.
- [x] Binary market: Report on market by selecting an outcome and signing the transaction.
- [x] Categorical market: Report on market by selecting an outcome and signing the transaction.
- [x] Scalar market: Report on market by entering an outcome and signing the transaction.
- [x] Verify that you can submit a report with an account that has no REP.
- [x] The market should be removed from the Reporting: Markets page and move to the Reporting: Dispute page. It should be listed under "Upcoming Dispute Window". This should happen without page refresh.
- [x] Verify the tentative winning outcome shown on the market card on the Reporting: Dispute page is correct.
- [ ] While the market is in the dispute window, settle a couple trades on another market so some reporting fees are generated. Then, push time forward to end the dispute windoow (without disputing the tenative winning outcome on your market) so your market resolves. Verify that you can collect the no-show bond that was used as stake on your market, the no-show gas bond, and your portion of ETH reporting fees on the Portfolio: Reporting page. The balance should be shown, and you should be able to claim that balance with the Claim All button.

## Upcoming Reporting

- [x] Verify that the markets listed in Upcoming Reporting are markets where the user is the Designated Reporter.



## Notes

Account balances can be seen using flash get-balance script. However, balances should also be checked in the UI.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
