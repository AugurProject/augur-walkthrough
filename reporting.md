# Testing Reporting:

This section focuses on the Initial Reporting Process.

In order for an initial report to occur the market's end time has to elapse. flash scripts can be used to set timestamp within designate reporting or open reporting. Designate reporting timeframe is a 3 day window starting 1 second after market end time. Open reporting timeframe starts 1 second after designate reporting ends and doesn't have an end time. Two scenarios are covered here.

  * Designate Report
  * Open Report

## Designate Report

Navigate to Reporting -> Reporting to see the markets in designate reporting state. 

- [ ] Verify only the designated reporter can report
- [ ] Report on market, select outcome and sign transaction
- [ ] Verify REP balance was deducted (If market creator and desigate reporter accounts are the same there's no balance change)
- [ ] Verify the market's tentative winning outcome is correct

## Open Report

Navigate to Reporting -> Reporting to see the markets in open reporting state.

- [ ] Verify anyone can report on market both designate reporter or other account
- [ ] Report on market, select outcome and sign transaction
- [ ] Verify no REP is needed to open report
- [ ] Verify the market's tentative winning outcome is correct



## Notes

Tentative winner can be verified on the Reporting -> Dispute view. Account balances can be seen using flash get-balance script. 