# Testing Forking:

This section focuses on operations in forking state. Flash scripts can be used to force market to forking state.

  * Pre-Fork
  * Forking Market
  * Migrating REP
  * Forking Ends
  * Migrating Markets
  * Disavow REP

## Pre-Fork

This state occurs when at least one dispute bond is greater than 2.5% of all REP, but no dispute bonds of that size have been filled yet. In other words, we're in a state where a fork _may_ occur, but hasn't yet.

- [x] The potentially forking market should be the first market listed on the Dispute page.
- [x] The potentially forking market should have a red bar along the top, and be labeled with "Potential Fork" (see mocks).
- [x] The outcomes with a dispute bond greater than 2.5% of all REP should have a red "!" icon to the left of the outcome name (see mocks).
- [x] ~~[ch10767](https://app.clubhouse.io/augur/story/10767/fork-not-caused-when-2-5-rep-dispute-bond-filled)~~ Filling the dispute bond that's at least 2.5% of all REP should trigger the During Fork state.

## During Fork

Initiate a fork and then test the follow:

- [x] Verify there is a forking banner along the top of the app (directly below the core stats bar) and that this is visible throughout the whole app.
- [x] "Additional Details" in the forking banner should be clickable to expand the additional details section.
- [x] ~~[ch10772](https://app.clubhouse.io/augur/story/10772/design-for-forking-additional-details-needs-to-be-adjusted)~~ Styles for the additional details section should match the design.
- [x] Verify that the forking window end date is correct, both in the header ("Forking Window Ends...") and in the paragraph ("The forking period will end...").
- [x] Verify that the forking progress bar progress and "X days left" is correct.
- [x] Verfiy that when the forking progress bar is nearly complete, the "X days left" text switches to the left side of the progress bar so it doesn't run off the page (see the Dispute progress bar for an example).
- [x] Clicking on the "Migrate REP" button should bring you to the Migrate REP form.
- [x] On the Dispute page, verify that the forking header is displaying (see mocks). (This is the same content as shown in the forking banner additional details.)
- [x] On the Dispute page, verify that the market that forced the fork is shown as the forking market.
- [x] That forking market should have a red bar across the top and be labeled with text that says "Forking" (see mocks).
- [x] ~~[ch10911](https://app.clubhouse.io/augur/story/10911/markets-that-were-in-dispute-don-t-move-down-to-dispute-paused)~~ Verify that all other markets that were already in Dispute are now listed under Dispute Paused.
- [x] Navigate directly to the dispute form for a market and verify that a dispute cannot be submitted.
- [x] ~~[ch10790](https://app.clubhouse.io/augur/story/10790/upcoming-dispute-window-should-change-to-dispute-paused-during-and-after-a-fork)~~ "Upcoming Dispute Window" should now be "Dispute Paused"
- [x] Verify that, after a market is reported on, it is moved to the "Dispute Paused" list.
- [x] The Create menu item should be disabled. If you navigate directly to the Create Market url, the tx to create a market should fail.
- [x] Verify that it is still possible to trade on markets, including the forking market.
- [x] Verify that the forking market can't be finalized during forking period. This can be attempted using the flash script.
- [x] ~~[ch11278](https://app.clubhouse.io/augur/story/11278/amount-shown-in-outstanding-balance-on-portfolio-reporting-forked-market-card-does-not-match-amount-migrated)~~ ~~[ch11188](https://app.clubhouse.io/augur/story/11188/getting-errors-trying-to-claim-outstanding-returns-on-forking-market)~~ Verify that you can claim your REP from the forking market and that the REP is migrated to the appropriate universe.
- [ ] ~~[ch11265](https://app.clubhouse.io/augur/story/11265/can-t-claim-rep-from-failed-dispute-bond-on-forking-market)~~ Any markets that were in Dispute with partially or fully filled dispute bonds when the fork occurred should show empty dispute bonds and be in Round 0 after the fork begins. (These will be listed underneath the Dispute Paused heading.)

## Disavow REP

Any REP that the user had staked on a dispute in a non-forking market should be claimable when the Fork begins. Stake placed on a dispute in a forking market should not be claimable. Stake placed on a report on any market should not be claimable.

- [x] ~~[ch11120](https://app.clubhouse.io/augur/story/11120/for-disavowinig-crowdsourcers-clicking-claim-does-not-bring-up-a-tx-dialogue)~~ ~~[ch10912](https://app.clubhouse.io/augur/story/10912/can-t-claim-disavow-rep)~~ Add REP to a couple dispute bonds in a couple different rounds. Keep track of the total. Cause one of those markets to fork. (1) Verify that you can claim all of the REP you placed in dispute bonds in non-forking markets by clicking the "Claim All" button on the Portfolio: Reporting page. (2) Verify that the REP you staked on a dispute bond in the forking market is not claimable.
- [x] Prior to a fork, place stake on a report. Initiate a fork on that market. Verify that you cannot claim the stake you placed on the report.
- [x] Prior to a fork, place stake on a report. Initiate a fork on a different market. Verify that you cannot claim the stake you placed on the report.
- [x] Initiate a fork. Verify that you can still report on markets in Designated Reporting.
- [x] Initiate a fork. Verify that you can still report on markets in Open Reporting.
- [x] Initiate a fork. Verify that you can still report on markets whose end date passes after the fork begins. The market should move into Designated Reporting like normal.
- [x] ~~[ch11265](https://app.clubhouse.io/augur/story/11265/can-t-claim-rep-from-failed-dispute-bond-on-forking-market)~~ Prior to a fork, add REP to a dispute bond (but don't fill the bond). Initiate a fork on the same market. Verify that you can claim your REP from the failed dispute.
- [x] Prior to a fork, add REP to a dispute bond (but don't fill the bond). Initiate a fork on a different market. Verify that you can claim your REP from the failed dispute.

## Migrating REP

- [x] Verify user gets 5% bonus when migrating REP during the 60 day forking period both before 50% of REP has been migrated and after 50% of REP has been migrated. (This 5% bonus will be available in the child universe that the REP was migrated to.)
- [x] Verify that users can still migrate REP after the forking period ends.
- [x] Verify that the user doesn't get the 5% bonus if they migrate after the forking period has ended.
- [x] Verify that the user can't migrate REP if they don't have any.
- [x] Verify that the user can migrate REP to any outcome of forking market, including Market is Invalid.
- [x] Verify that the user can migrate REP to a chosen scalar outcome.
- [x] Verify that the user can migrate only some of their REP at a time. Verify balance after Tx confirmation.
- [x] Verify that the user can migrate all their REP at one time. Verify balance after Tx confirmation.
- [x] Initiate a fork and migrate at least 50% of REP (5.5 mil REP). Verify that the winning universe is declared. It should be labeled both in the Migrate REP form and on the Account: Universes page.
- [x] Initiate a fork and migrate less than 50% of REP. Verify that the winning universe is declared when the 60 day window ends and the market is finalized.
- [x] ~~[ch11120](https://app.clubhouse.io/augur/story/11120/for-disavowinig-crowdsourcers-clicking-claim-does-not-bring-up-a-tx-dialogue)~~ Verify that REP can be migrated after being disavowed.
- [x] Verify that the forking market can be manually finalized when the 60 day forking window ends (when less that 50% of REP has been migrated during that window). The flash script can be used to do this.

## Universe Page:

During and after a fork:

- [x] Migrate REP to an outcome/universe using the Migrate REP form. This should automatically create a universe for that outcome if it didn't already exist. Verify user can switch to universe on the Account: Universes page.
- [x] Verify user account balances update correctly when universe is changed. This should change on the Account page and in the Core Stats bar.
- [x] Verify that the forking universe is listed in the left-hand column and the child universes are listed in the middle column.
- [x] Switch around to a couple different universes. Verify that your current universe is always correctly labeled "Current".
- [x] Verify that the winning universe from fork is labeled as the winning universe.
- [x] Verify that the stats shown about each universe are correct (your REP, total REP, and # of markets).

## Migrating Markets

- [x] Verify the "Migrate" button only displays on the market card after a winning universe is declared via the 50% REP Migrated method.
- [x] Verify the "Migrate" button only displays on the market card after a winning universe is declared when the forking period ends and the forked market has been finalized (and less than 50% of REP has been migrated).
- [x] Verify market can't be migrated before a winning universe is declared.
- [x] Verify markets only migrate to the winning universe.
- [x] ~~[ch11140](https://app.clubhouse.io/augur/story/11140/when-markets-are-migrated-categories-do-not-show-up-in-child-universe)~~ Once a market has been migrated, its categories should display in the child universe.
- [x] Verify that you can migrate a market in pre-reporting.
- [x] Verify that you can migrate a market in designated reporting.
- [x] Verify that you can migrate a market in open reporting.
- [x] Verify that you can migrate a market in Dispute Paused.
- [x] Verify that if a market was already reported on in the forking universe, the report and associated REP get migrated with the market.
- [x] Verify markets are no longer listed in the parent universe after they are migrated.
- [x] Verify anyone can migrate markets after a winning universe is declared.
- [x] Verify that trading on a migrated market works in the child universe.
- [x] Verify that the migrated market can go through the normal reporting & dispute cycle after migration to the child universe.

## Child Universes

Blocking: ~~[ch11265](https://app.clubhouse.io/augur/story/11265/can-t-claim-rep-from-failed-dispute-bond-on-forking-market)~~

- [x] Prior to a fork, place stake in a report. Initiate a fork on that market, then cause the outcome you reported on to be the winning outcome. Claim your REP from the forking market via the Portfolio: Reporting page, switch to the universe corresponding to your report, and verify that your REP from that report + 50% ROI is there.
- [ ] Prior to a fork, place stake in a report. Initiate a fork on that market, then cause a _different_ outcome to be the winning outcome. Claim your REP from the forking market via the Portfolio: Reporting page, switch to the universe corresponding to your report, and verify that your REP + 50% ROI is there. Then, switch to the winning universe, and verify that the REP from your report is _not_ there.
- [x] Prior to a fork, fill a dispute bond on a market to cause a successful dispute. Force a fork on the same market, then cause the outcome you placed dispute stake on to be the winning outcome. Claim your REP from the forking market, switch to the universe corresponding to your dispute stake, and verify that you can claim your REP from that dispute + 50% ROI.
- [ ] Prior to a fork, fill a dispute bond on a market to cause a successful dispute. Force a fork on the same market, then cause a _different_ outcome to be the winning universe. Claim your REP from the forking market, switch to the universe corresponding to your dispute stake, and verify that you can claim your REP from that dispute + 50% ROI.
- [x] Verify that a child universe starts out with no markets.
- [x] Verify you can create markets in a child universe and that the created market only shows up in the child universe.
- [x] Verify that you can trade on markets in a child universe.
- [x] Verify that the reporting & dispute cycle works in the child universe.
- [x] Cause a fork in the child universe, migrate REP to an outcome, then check the Universes page. The current universe should be shown in the middle column, the parent universe in the left column, and the child universes of the current universe should be shown in the right column. (see ch7720 for a more detailed description)
- [x] Cause one of the child universes from the most recent fork to be declared the winning outcome. Make sure this is labeled on the Universe page.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
