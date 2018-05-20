# Testing Markets List:

This section of the walk through will focus on the Markets List.

## General View

Load up Augur and Navigate to the "Markets" tab on the sidebar.

*Verify:*

- [x] Assuming there are more than 10 markets in this universe, confirm that we are properly paginating in chunks of 10.
- [x] The sidebar should have 1 submenu displaying (categories)
- [x] The sidebar submenu should list all the categories for every market that has been loaded.

Now look at each Market Card and verify the following:

*Verify that Market Cards Should:*
- [x] display category and tags in the top left corner of each card.
- [x] display the question for the market
- [x] display a scale with the current mid-price for the market.
- [x] verify the mid-price display is accurate and that the midprice moves along the scale appropriately. Test this for binary and scalar markets, and with something other than the default value (place some trades).
- [x] display labels for denominations on the scale for price.
- [x] display the min and max values accurately on either ends of the scale. (0% - 100% for binary markets, min - max for scalar markets)
- [x] display stats about volume, settlement Fee, and Expiration Date
- [x] verify that the volume stat is accurate
- [x] verify that the settlement fee is the market creator fee + the current reporter fee
- [x] dislayed expiration date is in local time (with appropriate utc offset labeled)
- [x] display a togglable favorites star to the left of the action button on the bottom right of the card.
- [x] display an action button that reads "trade" which when clicked brings you to the trade view for that market.
- [x] clicking on the market title brings you to the trade view for that market.
- [x] display the top 3 outcomes for a Categorical Market, with a "+ N More" where N is the number of remaining outcomes
- [x] display the other outcomes when the "+ N More" text is clicked on a Categorical Market.
- [x] "+ N More" should change to "- N More" when expanded, should collapse again on click.

## Filtering

Click on one of the categories in the first subSideBarMenu (1-SSB).

*Verify:*
- [x] The 2nd subSideBarMenu (2-SSB) slides out to the right of 1-SSB
- [x] 2-SSB should be populated with the tag values for the markets displayed
- [x] Markets displayed should be filtered to only show markets with a category equal to the selected category tag in 1-SSB
- [x] Clicking on one or more of the tags in 2-SSB should filter out markets that don't match the Category and Tag(s) selected. The logic for selection is `Category && (Tag1 || Tag2)`
- [x] Click on "Market" button on the Side Bar to reset the page to showing all markets.

## Search

Click on the search bar on the top of the page.

Enter in a keyword to search for, such as "augur" and "Augur". 

*Verify:*
- [x] The markets should be filtered to only show you markets where the search keyword matches info on that market.
- [x] The markets shown should include _all_ markets that match the keyword entered in the search.
- [x] Clicking the X on the search bar (right side) should clear Search and show all markets again (still paginated of course).
- [x] Search should not be case sensitive
- [ ] Markets should be searchable by title, tag, or category.


[Back to Main Menu/Intro](https://github.com/AugurProject/augur-walkthrough/)
