# Testing Markets List:

This section of the walk through will focus on the Markets List.

## General View

Load up Augur and Navigate to the "Markets" tab on the side bar.

*Verify:*

- [ ] Assuming there are more than 10 markets in this universe, confirm that we are properly paginating in chunks of 10.
- [ ] The side bar should have 1 submenu displaying 
- [ ] The side bar SubMenu should list all the categories for every market that has been loaded.

Now look at each Market Card and *Verify* the following:

*Verify that Market Cards Should:*
- [ ] display the category and tags in the top left corner of each card.
- [ ] display the question for the market
- [ ] display a scale with the current mid-price for the market.
- [ ] display labels for denominations on the scale for price.
- [ ] display the min and max values accurately on either ends of the scale. (min left side, max right side)
- [ ] display stats about volume, settlement Fee, and Expiration Date
- [ ] dislayed expiration date is in local time (with appropriate utc offset labeled)
- [ ] display a togglable favorites star to the left of the action button on the bottom right of the card.
- [ ] display a action button that reads "trade" which when clicked brings you to the trade view for that market.
- [ ] display the top 3 outcomes for a Categorical Market, with a "+ N More" where N is the number of remaining outcomes
- [ ] display the other outcomes when the "+ N More" text is clicked on a Categorical Market.

## Filtering

Click on one of the categories in the first subSideBarMenu (1-SSB).

*Verify:*
- [ ] The 2nd subSideBarMenu (2-SSB) slides out to the right of 1-SSB
- [ ] 2-SSB should be populated with the tag values for the markets displayed
- [ ] Markets displayed should be filtered to only show markets with a category equal to the selected category tag in 1-SSB
- [ ] Clicking on one or more of the tags in 2-SSB should filter out tags and markets that don't match either the Category or Tag(s) selected.

click on "Market" button on the Side Bar to reset the page to showing all markets.

## Search

Click on the search bar on the top of the page.

Enter in a keyword to search for, such as "augur". 

*Verify:*
- [ ] The markets should be filtered to only show you markets with the keyword searched matches info on that market.
- [ ] All markets shown shouldn't leave out markets that you know should match the keyword entered in the search but don't appear to filter.
- [ ] Clicking the X on the search bar (right side) should clear Search and show all markets again (still paginated of course).


[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)