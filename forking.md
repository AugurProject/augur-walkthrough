# Testing Forking:

This section focuses on operations in forking state. Flash scripts can be used to force market to forking state.

  * Forking Market
  * Migrating REP
  * Forking Ends
  * Migrating Markets
  * Disavow REP

## Forking Market

- [ ] Verify there is a forking banner
- [ ] Verify that the market that forced the fork is shown as the forking market
- [ ] Verify no markets can be created
- [ ] Verify trades are still possible on markets, including forking market


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
- [ ] Verify markets only migrate to winning outcome universe
- [ ] Verify anyone can migrate markets during forking period

## Disavow REP

To test this behavior user needs to have REP staked on successful dispute. This needs to occur before forking period begins. This way user can disavow their REP when market goes into fork.

- [ ] Verify REP can be disavowed during forking period
- [ ] Verify REP balance is correct after disavowed
- [ ] Verify REP can be migrated after being disavowed