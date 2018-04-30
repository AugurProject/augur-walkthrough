Augur Walkthrough
==================

# Intro:

This guide assumes you  are running a local environment and you have access to multiple accounts for testing with access to ETH and REP. We are also under the assumption that you are using Metamask for ease of testing. 

# Testing Accounts:

## Deposit Page:

Login to a metamask account with no REP but does have ETH.

Navigate to the Account Page using the sidebar.

You should be greated with the "Deposit" page.

*Verify* that your ETH balance, REP balance, and Account Address are all accurately displaying.

*Verify* that clicking on the address will copy the address to your clipboard.

## REP Faucet Page:

Navigate to the "Rep Faucet" page, we will check in on the "Withdraw" page after.

Click on the "Get REP" button.

Sign the transaction that appears in Metamask.

After the transaction completes, verify that you now have `47.00 REP`.

## Withdraw Page:

Now navigate to the "Withdraw" page.

Send some ETH to another Account you have access to.

Send some REP to another Account (prefereably the same address for easy verification) you have access to.

After both transactions complete, login to the account you sent the ETH and REP to, and *Verify* that you have recieved the ETH and REP from the first Account.

# Testing Create Market:

Navigate to the "Create" page on the sidemenu. In order to see the "create" menu item on the side bar you must be logged into an account.

In order to create a market, you will need to use an account that has both ETH and REP to cover the bonds and fees required to create a market.

## General:

When you navigate to the "create" page you should be greated by the first form page asking for the following:

Market Question
Category
Tag 1
Tag 2

*Verify:* 

A Market must have a Market Question and a Category.
Tags are optional.
Tags cannot match each other or the Category.

After you have entered some information and confirmed the validation is working, click the "Next: Outcome" button.

## Binary Market:

The next page should display just 3 radio buttons at first, unfilled, labeled as follows: "Yes/No", "Multiple Choice", and "Numerical Range".

Select "Yes/No". 

*Verify:* You should be greeted with a single input for "Additional Information". This is an optional field.

Click on "Next: Resolution"

You should now see 4 input sections: "Resolution Source", "Designated Reporter", "Expiration Date", and "Expiration Time". 

*Verify:*

- Each section is required.

- If you select "Outcome will be detailed on a public website" you should see a text input appear to allow website to be entered. This input should be required if shown.

- If you select "Someone Else" in the "Designated Reporter" section, then you should see a text input appear and you should be required to enter an ethereum address if this input is shown.

- Confirm that the Datepicker doesn't allow you to choose a day in the past. 

Click on "Next: Liquidity"

The Liquidity page should be asking you for a Settlement Fee as the first input. 

*Verify* That settlement Fee is required and must be a number between 0 and 100.

Under the Settlement Fee input you will see a Order Form and a Market Depth Chart and Order Book Chart displayed to the right of the form.

Here is where you can seed the market with liquidity by placing orders on the book immediately after creation succeeds. 

Placing orders is not required. However you should test that this is working, so place some orders on either side of the book.

*Verify:* 

- that orders must be priced between min and max value for the market.
- adding order should update the charts

During this time, keep track of approximately how much ETH you would need to place these orders as we will want to confirm that on the next page and after the orders have all been placed. 

Click on "Next: Review"

On this page we should see a breakdown of our costs. 

*Verify:* That the broken down stats appear to be accurate.

Click on "Submit" and sign the transaction. 

You should be redirected to the "Portfolio: Transaction" page.

