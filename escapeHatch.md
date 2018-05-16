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
- [x] ~~[ch10627](https://app.clubhouse.io/augur/story/10627/escape-hatch-with-create-market-funds-to-withdraw-incorrect)~~ The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] ~~[ch10628](https://app.clubhouse.io/augur/story/10628/after-withdrawing-funds-review-screen-continues-to-be-shown)~~ After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Participation Tokens

With a fresh account (with no previous txs) purchase PTs in the current fee window. Keep track of the total.

Pull the escape hatch.

- [x] ~~[ch10630](https://app.clubhouse.io/augur/story/10630/pts-are-not-redeemable-through-the-escape-hatch-modal)~~ The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Designated Report

With a fresh account (with no previous txs) create a market and assign yourself as the designated reporter. Move time forward and submit a designated report. Keep track of the total (including the market creation bonds you should get back).

Pull the escape hatch.

- [x] ~~[ch10431](https://app.clubhouse.io/augur/story/10431/escape-hatch-modal-does-not-appear)~~ The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Initial Report (on market in Open Reporting)

With a fresh account (with no previous txs) move time forward so one of the default-created markets moves into Open Reporting. Submit a report. Keep track of the total.

Pull the escape hatch.

- [x] ~~[ch10431](https://app.clubhouse.io/augur/story/10431/escape-hatch-modal-does-not-appear)~~ The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Dispute Bond (filled)

With a fresh account (with no previous txs) move time forward so one of the default-created markets moves into Open Reporting. Submit a report. Move time one week, to put the market in dispute phase, Dispute on an outcome and fill the bond, Keep track of the total.

Pull the escape hatch.

- [x] The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Dispute Bond (partially filled)

With a fresh account (with no previous txs) move time forward so one of the default-created markets moves into Open Reporting. Submit a report. Move time one week, to put the market in dispute phase, Dispute on an outcome and **partially** fill the bond, Keep track of the total.

Pull the escape hatch.

- [x] The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Trading - Open Order

[ch10734](https://app.clubhouse.io/augur/story/10734/add-shares-to-escape-hatch)

With a fresh account (with no previous txs) place an order on a market. Keep track of the total.

Pull the escape hatch. The TXs presented will including claiming escrowed shares, which will update the funds available, and then more TXs will appear to claim those funds.

- [ ] The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [ ] The withdraw funds button should bring up a Review screen.
- [ ] The amount of funds available to withdraw should be correct. 
- [ ] The tx(s) to withdraw should succeed.
- [ ] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [ ] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

### Trading - Position

With a fresh account (with no previous txs) fill a market order so you have a position. Keep track of the total.

Pull the escape hatch.

- [x] The escape hatch modal should come up, with a message saying you have funds to withdraw.
- [x] The withdraw funds button should bring up a Review screen.
- [x] The amount of funds available to withdraw should be correct. 
- [x] The tx(s) to withdraw should succeed.
- [x] After you've withdrawn the available funds, you should be shown the "no funds" escape hatch message. 
- [x] Your total funds should reflect your new, correct balance (minus gas for the withdraw tx).

## Notes

Account balances can be seen using flash get-balance script. However, balances should also be checked in the UI.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
