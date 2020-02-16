# Mike Schmitt - Enodo UI Challenge Submission

Hello, Enodo team! Thank you for taking the time to review my submission. Below you will find high-level developer notes on my work, in addition to the proposed improvements.

## Developer Notes

* **Vue.js** - seeing as this is the framework endorsed by the team, I chose to learn and utilize Vue.js to build out the interface
* **Vue Material** - the core UI components were built with Vue Material
* **Scoped Component Styling** - the styling approach, as you'll see, was implemented at the component level utilizing SCSS
* **Data** - modified the data values and fields listed in the Historical Operating Expenses to match the mockup

## Improvements
1. **Tabular Main Content** - the Gross Potential Rent, Operating Expenses, and Historical Operating expenses can become the main focus of the page by repositioning the lateral navigation menu. Given this, the *Property Summary* card can either be toggled hidden/shown with a button in the secondary navigation bar, or broken down into tabs (Summary, Comparables, Expenses, etc.) to utilize the open space within the secondary navigation bar. If the design added this, it would allow the user to focus on the data/insights while still allowing easy access to the higher level details provided in the *Property Summary*.

2. **Data Context** - seeing as I'm not a regular user of a platform in this industry, there could be a dedicated space to providing context to what the different plots are showing, key totals, variables, etc. There is a "Help" icon in the main navigation bar, but having an option for the user to naturally learn about the representation of the data themselves would make the experience incredibly smooth. The first example that comes to mind is something similar to TurboTax (Marc brought this up in our initial conversation) and how simple it is to gain clarification on something without hunting through a Google search.

3. **Single NavBar** - to optimize the available space on any given screen, the content of the secondary navigation bar can be absorbed by either the NavBar above it, or into the *Property Summary* card, ultimately getting rid of it. If the menu items in the main navigation bar are condensed (dropdown or smaller), and the laternal navigation in the *Property Summary* is recategorized and binned into its own dropdown within the main navigation bar, there is now a larger canvas to display charts, graphs, and data tables.  

```
