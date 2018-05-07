# Testing Accounts:

This section of the walk through focuses on the Account Page and it's functions. All of the Account functions should be tested with each authentication method.

## Authentication:

Load up the UI and make sure you're logged out of any authentication method. You should be greated with the categories page and your side bar should only have two options.

*Verify:*
- [ ] when not logged into an account, only "Markets" and "Account" should be options on the sidebar

Click on the "Account" menu.

*Verify:*
- [ ] should now be on an auth screen, with two options, "Connect" and "Create"

## Create Account:

Clicking on the "Create" button will give you instructions on how to download the uport app. Follow the instructions to test uPort account creation.

After creating a uPort account, scan the QR code.

*Verify:*
- [ ] after accepting on your mobile device, you should be logged into your Augur account

## Connect Account:

If you are logged in, hard refresh (ctrl + R / cmd + R) the app (and logout of metamask if needed).

Navigate to the "account" menu again, this time click "Connect"

*Verify:*
- [ ] you can successfully login to metamask
- [ ] you can successfully login to a Ledger Wallet (make sure browser data and contract data is enabled on ledger)
- [ ] you can successfully login to uPort (through the connect menu's QR code)

To verify the above, you will need to hard refresh/logout after each verified login. 

## Deposit Page:

Test the following with each authentication type. Log in, then navigate to the Account Page using the sidebar. You should be greated with the "Deposit" page.

*Verify:* 

With Metamask:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.

With uPort:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.

With Ledger:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.

## REP Faucet Page:

Test the following with each authentication type. Log in, then navigate to the "Rep Faucet" page, we will check in on the "Withdraw" page after.

Click on the "Get REP" button.

Sign the transaction that appears in Metamask.

After the transaction completes *verify:*
- [ ] you now have `47.00 REP`.

## Withdraw Page:

Now navigate to the "Withdraw" page.

Send some ETH to another Account you have access to.

Send some REP to another Account (prefereably the same address for easy verification) you have access to.

After both transactions complete, login to the account you sent the ETH and REP to.

*Verify:* 
- [ ] the second Account recieved the ETH and REP from the first Account.

## Universe Page:

Flash scripts can be used to force fork, need to migrate 5.5 mil REP to force forking market finalization.

- [ ] Verify user can switch to universe listed
- [ ] Verify user account balances update correctly when universe is changed
- [ ] Verify genesis universe is listed
- [ ] Verify winning universe from fork is listed

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
