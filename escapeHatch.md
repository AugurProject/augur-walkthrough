# Testing the Escape Hatch:

This section focuses on the use of the various escape hatch methods once emergency mode has been activated.

To flip the escape hatch simply use the flash script `flash escape-hatch`

There are 5 different methods available to users to salvage funds when the escape hatch has been pulled, but it is all condensed into a single dialog and interaction within the UI. To correctly test the escape hatch however you must have funds available throughout the system in such a way that this UI will excersise all 5 methods.

The populated geth node will already have some of this set up for you since it creates markets.

Pulling the escape hatch is done with this command:

```
flash escape-hatch
```

## Variations

### No Funds

- [x] Pull the escape hatch while logged into a user account that has had no transactions. Verify that the escape hatch notice comes up, but with a message saying you have no funds to withdraw.

### Create Market bonds

With a fresh account (with no previous txs) create a market so you have funds locked up in the no-show bond, validity bond, and reporter gas bond. Keep track of the total.

Pull the escape hatch.

- [x] The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [ ] (FAILED) The amount of funds available to withdraw should be correct.
- [x] The tx(s) to withdraw should succeed.
- [ ] (FAILED) After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message.
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Participation Tokens

### Designated Report

### Initial Report (on market in Open Reporting)

### Dispute Bond (filled)

### Dispute Bond (partially filled)

### Trading

### All of the above


## Notes

Account balances can be seen using flash get-balance script. However, balances should also be checked in the UI.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
