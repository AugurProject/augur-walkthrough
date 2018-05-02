# Testing Create Market:

This section of the walk through focuses on the Create Market Process.

Navigate to the "Create" page on the sidemenu. In order to see the "create" menu item on the side bar you must be logged into an account.

In order to create a market, you will need to use an account that has both ETH and REP to cover the bonds and fees required to create a market.

### Define:

When you navigate to the "create" page you should be greated by the first form page asking for the following:

- Market Question
- Category
- Tag 1
- Tag 2

*Verify:* 

- [ ] A Market must have a Market Question and a Category.
- [ ] Tags are optional.
- [ ] Tags and Category must be unique.

After you have entered some information and confirmed the validation is working, click the "Next: Outcome" button.

### Outcome:

The Outcome section of the Create Market Form differs based on what option you select for the type of market you would like to create.

3 radio buttons are displayed at first, unfilled, and labeled as follows: "Yes/No", "Multiple Choice", and "Numerical Range".

In the following sections, "Binary Market", "Categorical Market", and "Scalar Market" we will go over the various modifications you might see on this Outcome's Page. You should make sure to test each permutation of market type, ideally more than once with varying values.

### Binary Market:

To create a Binary Market select "Yes/No". 

*Verify:* 
- [ ] You should be greeted with a single input for "Additional Information". This is an optional field.

Click on "Next: Resolution"

### Categorical Market:

To create a Categorical Market select "Multiple Choice". 

*Verify:* 
- [ ] You should see 8 smaller inputs under the "Potential Outcomes" label.
- [ ] The first two outcomes are required.
- [ ] Outcome names must be unique.
- [ ] You should be greeted with a input for "Additional Information" as well. This is an optional field.

Click on "Next: Resolution"

### Scalar Market:

To create a Scalar Market select "Numerical Range". 

*Verify:* 
- [ ] You should see 3 input boxes under the "Range Values" header, and an additional input under the "precision" header.
- [ ] Min Value is required, must be less than Max Value
- [ ] Max Value is required, must be greater than Min Value
- [ ] Denomination is an optional field to indicate the denomination of the range.
- [ ] Precision should be defaulted to `0.0001`.
- [ ] Precision is required.
- [ ] You should be greeted with a input for "Additional Information" as well. This is an optional field.

Click on "Next: Resolution"

### Resolution:

You should now see 4 input sections: "Resolution Source", "Designated Reporter", "Expiration Date", and "Expiration Time". 

*Verify:*

- [ ] Each section is required.
- [ ] If you select "Outcome will be detailed on a public website" you should see a text input appear to allow website to be entered. This input should be required if shown.
- [ ] If you select "Someone Else" in the "Designated Reporter" section, then you should see a text input appear and you should be required to enter an ethereum address if this input is shown.
- [ ] Confirm that the Datepicker doesn't allow you to choose a day in the past. 

Click on "Next: Liquidity"

### Liquidity:

The Liquidity page should be asking you for a Settlement Fee as the first input. 

*Verify:* 
- [ ] settlement Fee is required and must be a number between 0 and 100.

Under the Settlement Fee input you will see a Order Form and a Market Depth Chart and Order Book Chart displayed to the right of the form.

Here is where you can seed the market with liquidity by placing orders on the book immediately after creation succeeds. 

Placing orders is not required. However you should test that this is working, so place some orders on either side of the book.

*Verify:* 
- [ ] that orders must be priced between min and max value for the market.
- [ ] adding order should update the charts

During this time, keep track of approximately how much ETH you would need to place these orders as we will want to confirm that on the next page and after the orders have all been placed. 

Click on "Next: Review"

### Review:

On this page we should see a breakdown of our costs. 

*Verify:* That the broken down stats appear to be accurate.

Click on "Submit" and sign the transaction. 

You should be redirected to the "Portfolio: Transaction" page.

[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)