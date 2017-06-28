# Wednesday June 21

## Tradecraft Meeting

1. Sign In page
2. Placeholder Job Search - Activity Detail
	* two tags/states are "Open" and "Deactivated" (matches color on sidebar)
	* Can edit the Title & Stage when you click "Edit" button
	* Kanban-style
	* drag and drop if possible
	* Edit is just the titles of each list (in-place on title - not on an extra modal)
	* All Delete actions have a confirmation; initially built-in JS one works
	* Eventually want to log everything that happens somewhere - track & visualize changes over time (Google Analytics for brand changes over time)
	* Empty state - "Find Companies" and nothing else in other parts of funnel
	* For now, Delete removes entire column (sidebar updates)
	* Scrolls to the right -- so same as Trello
3. Activities List
	* "Data Points" - things like "Last Updated" / "Created By" / "Count" 
	* "Add New Activity" button is not high-priority
4. Company Search
	* "Advanced Filtering" slides down to show more
	* just filtering; no text input
	* include Environment search
	* Sort By - "Creation Date" (Reverse Chronological/Most Recent)  
	* "Add" button adds a company
5. Company/Agent detail
	* "Potential Employer" can just be static text 
	* sidebars should be collapsible & responsive
	* MVP just need Notes
	* editing notes can be a modal from w/ Save or Cancel
	* Notes are attached to different states (ex. Stage 1/2/3 -- aka Research, Apply, Follow Up)
	* Empty state "There are no assets" - "Add" button adds a new asset category (Employees / Funding / Brand)
	* "Last Updated"/"Created Date"/"Created By"
	* If you change the stage in the right dropdown, it also changes what is selected on the sidebar
6. Asset detail 
	* Companies have assets, assets have sub-assets (Brand > Logo)  
	* Breadcrumb will show up below brand name in asset view (click company name to go back to agent detail view)
	* "Add" button adds component to asset

### Notes

* Agent - anyone with decision-making power - ex. company
* Asset - agents have assets (brand, employees)

* Top bar is location filter; "US Economy" is static text - SF drop-down sets the scope for the search - drop down that you can type in (Selectize country selector) -- https://github.com/selectize/selectize.js -- "Environment Search" -- if possible, save for last
	* Leave it empty on particular agent pages

* Sidebar can be expanded and collapased by the user (not automatic)	
	* "Browse Companies" takes you to search results of all companies that fit your most recent last search filters -- results are dynamic, but query/filters are static
	* If you open it, it stays open

* Two types of editing - full-page view (larger) & modal forms (smaller)

* Make sure it works for Tablet size - 768px (tablet) -- 1440 (max possible screen)
* Content always 12 columns; sidebars can be fixed based on the screen size 
	* 300px @ 1440 width -- 24% of width
	* Tablet view can be collapsed state

* Preference with icons is SVG 

* Sign In page -- 6 offset, 5 across (out of 12)

* Systemitize font sizes relative to root font size; by ems (change the body font at diff breakpoints)

### Saved Links

* Organizing Components
	* [Organizing Components in Large React App](https://www.sitepoint.com/organize-large-react-application/)
	* [Composition over Inheritance](https://facebook.github.io/react/docs/composition-vs-inheritance.html)
* SASS
	* [Bootstrap Sass](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap/mixins/_grid.scss) 
	* [NPM Boostrap-sass](https://www.npmjs.com/package/bootstrap-sass)
	* [SCSS vs. Sass](https://stackoverflow.com/questions/5654447/whats-the-difference-between-scss-and-sass)
	* [NPM Boostrap Grid](https://www.npmjs.com/package/bootstrap-grid)
	* 
* SVG Images
	* [NPM react-svg](https://www.npmjs.com/package/react-svg)
	* [NPM React-SVG-Loader](https://www.npmjs.com/package/react-svg-loader)
	* [Importing SVGs as React components](https://github.com/facebookincubator/create-react-app/issues/1388)
	* 
* Login Background Responsive Image
	* [NPM React Native Responsive Images](https://www.npmjs.com/package/react-native-responsive-image)
	* [NPM React Responsive Image](https://www.npmjs.com/package/react-responsive-image)
	* [NPM React Image Responsive](https://www.npmjs.com/package/react-image-responsive)
	* [Responsive Images](https://www.sitepoint.com/how-to-build-responsive-images-with-srcset/)
* CSS Naming Conventions
	* [BEM](https://css-tricks.com/bem-101/)
* Drag & Drop
	* [React DnD](http://react-dnd.github.io/react-dnd/)
* Accordion Menus
	* [One](https://codepen.io/cssjockey/pen/ckAFs)
	* [Two](https://codepen.io/Pavan_Yuvan/pen/gPMdxR?editors=1100)
	* [Three](https://www.bootply.com/fe4AfcEnKD)
	* [Four](https://www.w3schools.com/howto/howto_js_accordion.asp)
* 




## [Patterns on Heroku](http://patterns-staging.herokuapp.com/)




************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 