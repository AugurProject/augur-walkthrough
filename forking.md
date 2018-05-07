# Testing Forking:

This section focuses on operations in forking state. Flash scripts can be used to force market to forking state.

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

## Migrating REP

- [ ] Verify user gets 5% bonus when migrating REP during fork period
- [ ] Verify user can't migrate REP if they don't have any
- [ ] Verify user can migrate REP to any outcome of forking market
- [ ] Verify user can migrate some of their REP, verify balance after Tx confirmation
- [ ] Verify user can migrate all their REP, verify balance after Tx confirmation
- [ ] Verify outcome winner is declared when 50% REP supply has been migrated (5.5 mil REP)

## Forking Ends

A user has to manually call market finalization if 50% of REP isn't migrated and the forking period has ended. Use flash script to finalize market.

- [ ] Verify winning outcome is chosen, when less than 5.5 mil REP has been migrated
- [ ] Verify user doesn't get a bonus after forking period has ended

## Migrating Markets

- [ ] Verify market can't be migrated during forking period
- [ ] Verify markets only migrate to winning universe
- [ ] Verify anyone can migrate markets during forking

## Disavow REP

To test this behavior user needs to have REP staked on dispute rounds. This needs to occur before forking period begins. Disputes can't occur during forking period. This way user can disavow their REP when market goes into fork.

- [ ] Verify REP can be disavowed during forking period
- [ ] Verify REP balance is correct after disavowed
- [ ] Verify REP can be migrated after being disavowed
- [ ] Verify REP on failed dispute rounds can be disavowed

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
