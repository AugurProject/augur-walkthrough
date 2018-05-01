# Testing Accounts:

This section of the walk through focuses on the Account Page and it's functions.

## Authentication:

When you first load up the UI, assuming you haven't enabled and logged into metamask, you should be greated with the categories page and your side bar should only have two options.

*Verify:*
- [x] when not logged into an account, only "Markets" and "Account" should be options on the sidebar

Click on the "Account" menu.

*Verify:*
- [x] should now be on an auth screen, with two options, "Connect" and "Create"

## Create Account:

Clicking on the "Create" button will give you instructions on how to download the uport app. Follow the instructions to test uport integration.

After creating a uport account, scan the QR code.

*Verify:*
- [x] after accepting on your mobile device, you should be logged into your Augur account

## Connect Account:

If you are already logged in, hard refresh (ctrl + R / cmd + R) the app (and logout of metamask if you logged in using metamask).

Navigate to the "account" menu again, this time click "Connect"

*Verify:*
- [x] you can successfully login to metamask
- [x] you can successfully login to a Ledger Wallet (make sure browser data and contract data is enabled on ledger)
- [x] you can successfully login to uport (through the connect menu's QR code)

To verify the above, you will need to hard refresh/logout after each verified login. 

## Deposit Page:

Login to an account with no REP but does have ETH.

Navigate to the Account Page using the sidebar.

You should be greated with the "Deposit" page.

*Verify:* 
- [x] your ETH balance accurately displays.
- [x] your REP balance accurately displays. 
- [x] your Account Address accurately displays.
- [x] clicking on the Account Address will copy the Address to your clipboard.

## REP Faucet Page:

Navigate to the "Rep Faucet" page, we will check in on the "Withdraw" page after.

Click on the "Get REP" button.

Sign the transaction that appears in Metamask.

After the transaction completes *verify:*
- [x] you now have `47.00 REP`.

## Withdraw Page:

Now navigate to the "Withdraw" page.

Send some ETH to another Account you have access to.

Send some REP to another Account (prefereably the same address for easy verification) you have access to.

After both transactions complete, login to the account you sent the ETH and REP to.

*Verify:* 
- [x] the second Account recieved the ETH and REP from the first Account.

## Universe Page:

The Universe Page walkthrough will come a bit later, it requires flash and some forking and is more advanced then the other account pages.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)