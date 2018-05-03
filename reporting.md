# Testing Reporting:

This section focuses on the Initial Reporting Process.

In order for an initial report to occur the market's end time has to elapse. flash scripts can be used to set timestamp within designate reporting or open reporting. Designate reporting timeframe is a 3 day window starting 1 second after market end time. Open reporting timeframe starts 1 second after designate reporting ends and doesn't have an end time. Two scenarios are covered here.

  * Designate Report
  * Open Report

## Designate Report

Navigate to Reporting -> Reporting to see the markets in designate reporting state. 

- [ ] Create a market where the market creator is the designated reporter and then move time forward so the market is in the DR stage. Verify that only the market creator can see the market listed under Designated Reporting, and verify that only the market creator can report on the market.
- [ ] Create a market where the someone other than the market creator is the designated reporter. Then, move time forward so the market is in the DR stage. Verify that only the designated reporter can see the market listed under Designated Reporting, and verify that only the designated reporter can report on the market.
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

## Open Report

Navigate to Reporting -> Reporting to see the markets in open reporting state.

- [ ] Verify that a market moves into Open Reporting when the 3-day DR window is up. This should happen without page refresh.
- [ ] Verify that anyone can report on a market in Open Reporting. Try this with an account other than the market creator and designated reporter.
- [ ] Binary market: Report on market by selecting an outcome and signing the transaction.
- [ ] Categorical market: Report on market by selecting an outcome and signing the transaction.
- [ ] Scalar market: Report on market by entering an outcome and signing the transaction.
- [ ] Verify no REP is needed to open report.
- [ ] The market should be removed from the Reporting: Markets page and move to the Reporting: Dispute page. It should be listed under "Upcoming Dispute Window". This should happen without page refresh.
- [ ] Verify the tentative winning outcome shown on the market card on the Reporting: Dispute page is correct.



## Notes

Account balances can be seen using flash get-balance script. 

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
