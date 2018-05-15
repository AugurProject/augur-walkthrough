# Testing the Escape Hatch:

This section focuses on the use of the various escape hatch methods once emergency mode has been activated.

To flip the escape hatch simply use the flash script `flash escape-hatch`

There are 5 different methods available to users to salvage funds when the escape hatch has been pulled, but it is all condensed into a single dialog and interaction within the UI. To correctly test the escape hatch however you must have funds available throughout the system in such a way that this UI will excersise all 5 methods.

The populated geth node will already have some of this set up for you since it creates markets.

## Getting funds to be trapped

Before placing funds into the system keep track of what you initially start with. This value will be needed later

 - [ ] Purchase Participation tokens in the reporting UI
 - [ ] Do a designated or initial report on a market
 - [ ] Participate in at least one market dispute (The market does not need to finalize)
 - [ ] Purchase shares in a market either by filling an order or by purchasing complete sets
 - [ ] Create a market so you have some REP held in bonds

 Keep track of the funds 

## Pull the escape hatch

Now that funds have been tied up in the systems you should pull the escape hatch

```
flash escape-hatch
```

## Use the escape hatch UI to get back funds

Now that the escape hatch has been pulled the UI should present a blocking modal dialog for the escape hatch.

 - [ ] Verify that the escape hatch dialog now appears and prevents interaction with the UI as normal
 - [x] Proceed by clicking "Withdraw all funds"
 - [x] Click the button to retrieve funds
 - [ ] You should get _many_ transaction approval messages. One for each market, one for participation tokens, one for the initial report, one for any dispute crowdsourcers you participated in, and one for each market you own shares in.
 - [ ] After approving the transactions your ETH and REP balance should be back to what it was initally but minus all of the gas that has been used to get this far.
 - [ ] Reload the UI and confirm that the dialog now does not present an option to "Withdraw all funds"


## Notes

Account balances can be seen using flash get-balance script. However, balances should also be checked in the UI.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
