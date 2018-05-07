# Testing Accounts:

This section of the walk through focuses on the Account Page and it's functions. All of the Account functions should be tested with each authentication method.

## Authentication:

Load up the UI and make sure you're logged out of any authentication method. You should be greated with the categories page and your side bar should only have two options.

*Verify:*
- [x] when not logged into an account, only "Markets" and "Account" should be options on the sidebar

Click on the "Account" menu.

*Verify:*
- [x] should now be on an auth screen, with two options, "Connect" and "Create"

## Create Account:

Clicking on the "Create" button will give you instructions on how to download the uport app. Follow the instructions to test uPort account creation.

After creating a uPort account, scan the QR code.

*Verify:*
- [x] after accepting on your mobile device, you should be logged into your Augur account

## Connect Account:

If you are logged in, hard refresh (ctrl + R / cmd + R) the app (and logout of metamask if needed).

Navigate to the "account" menu again, this time click "Connect"

*Verify:*
- [x] you can successfully login with metamask
- [ ] you can successfully login with a Ledger Wallet (make sure browser data and contract data is enabled on ledger)
- [x] you can successfully login with uPort (through the connect menu's QR code)
- [ ] you can successfully login with Trezor

To verify the above, you will need to hard refresh/logout after each verified login. 

## REP Faucet Page:

Test the following with each authentication type. Log in, then navigate to the "Account -> Rep Faucet" page.

*Verify:*

With Metamask:

- [x] Click the "Get REP" button. Verify that the transaction succeeds and that you receive a Confirmed notification.
- [x] Your balance should now have 47.00 more REP.

With uPort:

- [ ] Click the "Get REP" button. Verify that the transaction succeeds and that you receive a Confirmed notification.
- [ ] Your balance should now have 47.00 more REP.

With Ledger:

- [ ] Click the "Get REP" button. Verify that the transaction succeeds and that you receive a Confirmed notification.
- [ ] Your balance should now have 47.00 more REP.

With Trezor:

- [ ] Click the "Get REP" button. Verify that the transaction succeeds and that you receive a Confirmed notification.
- [ ] Your balance should now have 47.00 more REP.

## Withdraw Page:

Now navigate to the "Account -> Withdraw" page. You'll be sending REP and ETH to a second account that you have access to. In the following section (Deposit page), you'll be sendinig the REP and ETH back to your original account.

*Verify:* 

With Metamask:

- [x] Use the form to send some ETH to another Account you have access to.
- [x] Use the form to send some REP to another Account you have access to.
- [x] Verify the second Account recieved the ETH and REP from the first Account.

With uPort:

- [ ] Use the form to send some ETH to another Account you have access to.
- [ ] Use the form to send some REP to another Account you have access to.
- [ ] Verify the second Account recieved the ETH and REP from the first Account.

With Ledger:

- [ ] Use the form to send some ETH to another Account you have access to.
- [ ] Use the form to send some REP to another Account you have access to.
- [ ] Verify the second Account recieved the ETH and REP from the first Account.

With Trezor:

- [ ] Use the form to send some ETH to another Account you have access to.
- [ ] Use the form to send some REP to another Account you have access to.
- [ ] Verify the second Account recieved the ETH and REP from the first Account.

## Deposit Page:

Test the following with each authentication type. Log in, then navigate to the Account Page using the sidebar. You should be greeted with the "Deposit" page.

*Verify:* 

With Metamask:

- [x] your ETH balance accurately displays.
- [x] your REP balance accurately displays. 
- [x] your ETH balance in the Core Stats bar accurately displays.
- [x] your REP balance in the Core Stats bar accurately displays. 
- [x] your Account Address accurately displays.
- [x] clicking on the Account Address will copy the Address to your clipboard.
- [ ] Use the QR code to send some ETH to this account from another account you have access to.
- [ ] Use the QR code to send some REP to this account from another account you have access to.
- [ ] Verify you recieved the ETH and REP.

With uPort:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.
- [ ] Use the QR code to send some ETH to this account from another account you have access to.
- [ ] Use the QR code to send some REP to this account from another account you have access to.
- [ ] Verify you recieved the ETH and REP.

With Ledger:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.
- [ ] Use the QR code to send some ETH to this account from another account you have access to.
- [ ] Use the QR code to send some REP to this account from another account you have access to.
- [ ] Verify you recieved the ETH and REP.

With Trezor:

- [ ] your ETH balance accurately displays.
- [ ] your REP balance accurately displays. 
- [ ] your ETH balance in the Core Stats bar accurately displays.
- [ ] your REP balance in the Core Stats bar accurately displays. 
- [ ] your Account Address accurately displays.
- [ ] clicking on the Account Address will copy the Address to your clipboard.
- [ ] Use the QR code to send some ETH to this account from another account you have access to.
- [ ] Use the QR code to send some REP to this account from another account you have access to.
- [ ] Verify you recieved the ETH and REP.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
