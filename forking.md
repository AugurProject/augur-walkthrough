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

- [ ] The potentially forking market should be the first market listed on the Dispute page.
- [ ] The potentially forking market should have a red bar along the top, and be labeled with "Potential Fork" (see mocks).
- [ ] The outcomes with a dispute bond greater than 2.5% of all REP should have a red ! icon to the left of the outcome name (see mocks).

## Forking Market

- [ ] Verify there is a forking banner along the top of the app (directly below the core stats bar) and that this is visible throughout the whole app.
- [ ] "Additional Details" in the forking banner should be clickable to expand the additional details section.
- [ ] Verify that the forking window end date is correct, both in the header ("Forking Window Ends...") and in the paragraph ("The forking period will end...")
- [ ] Verify that the forking progress bar progress and "X days left" is correct
- [ ] Verfiy that when the forking progress bar is nearly complete, the "X days left" text switches to the left side of the progress bar so it doesn't run off the page (see the Dispute progress bar for an example)
- [ ] Clicking on the "Migrate REP" button should bring you to the Migrate REP form
- [ ] On the Dispute page, verify that the forking header is displaying (see mocks). (This is the same content as shown in the forking banner additional details)
- [ ] On the Dispute page, verify that the market that forced the fork is shown as the forking market
- [ ] That forking market should have a red bar across the top and be labeled with text that says "Forking" (see mocks).
- [ ] Verify that all other markets that were already in Dispute are now listed under Dispute paused
- [ ] Navigate directly to the dispute form for a market and verify that a dispute cannot be submitted
- [ ] Verify that, after a market is reported on, it is moved to the "Dispute Paused" list
- [ ] The Create menu item should be disabled. If you navigate directly to the Create Market url, the tx to create a market should fail.
- [ ] Verify trades are still possible on markets, including forking market
- [ ] Verify the forking market can't be finalized during forking period

## Disavow REP

To test this behavior the user needs to have REP staked on dispute rounds prior to when the Fork was initiated. Any REP that the user had staked on a dispute in a non-forking market should be claimable when the Fork begins.

- [ ] Add REP to a couple dispute bonds in a couple different rounds on a couple different markets. Keep track of the total. Cause one of those markets to fork. (1) Verify that you can claim all of the REP you placed in dispute bonds in non-forking markets by clicking the "Claim All" button on the Portfolio: Reporting page. (2) Verify that the REP you staked on a dispute bond in the forking market is not claimable.
- [ ] Prior to a fork, place stake on a report. Initiate a fork on that or another market. Verify that you cannot claim the stake you placed on a report.
- [ ] Initiate a fork. Verify that you can still report on markets.
- [ ] Add REP to a dispute bond (but don't fill the bond). Initiate a fork on the same market. Verify that you can claim your REP from the failed dispute.
- [ ] Add REP to a dispute bond (but don't fill the bond). Initiate a fork on a different market. Verify that you can claim your REP from the failed dispute.

## Migrating REP

- [ ] Verify user gets 5% bonus when migrating REP during fork period
- [ ] Verify user can't migrate REP if they don't have any
- [ ] Verify user can migrate REP to any outcome of forking market
- [ ] Verify user can migrate some of their REP, verify balance after Tx confirmation
- [ ] Verify user can migrate all their REP, verify balance after Tx confirmation
- [ ] Verify outcome winner is declared when 50% REP supply has been migrated (5.5 mil REP)
- [ ] Verify REP can be migrated after being disavowed

## Universe Page:

Flash scripts can be used to force fork, need to migrate 5.5 mil REP to force forking market finalization.

- [ ] Verify user can switch to universe listed
- [ ] Verify user account balances update correctly when universe is changed
- [ ] Verify genesis universe is listed
- [ ] Verify winning universe from fork is listed

## Forking Ends

A user has to manually call market finalization if 50% of REP isn't migrated and the forking period has ended. Use flash script to finalize market.

- [ ] Verify winning outcome is chosen, when less than 5.5 mil REP has been migrated
- [ ] Verify user doesn't get a bonus after forking period has ended

## Migrating Markets

- [ ] Verify market can't be migrated during forking period
- [ ] Verify markets only migrate to winning universe
- [ ] Verify anyone can migrate markets during forking

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
