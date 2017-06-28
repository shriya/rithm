# Monday June 19

## Git Merge & Rebase

* go back through commit history 
* `git rebase -i HEAD-3` takes you 3 commits before the HEAD 
* "squash" combines a commit with the previous commit & make new commit message
* "reword" means change the commit message
* when you rebase, it takes you to a different point in the history
* if one person committed on the master, and you committed locally -- you have to merge them together `git pull origin master` : need commit message for the merge (`git pull` is a fetch and a merge; if you only want to fetch you do a `git fetch`)
* if you do `git status` you can see if your branch is ahead or behind `master`
* **pull frequently!!** (we'll have slack notifications set up for company project groups)
* `git pull --rebase origin master` will put local changes on end of whatever's on github & rebase as you pull; this way you don't have an extra merge commit being added
* git will stop rebasing at first merge conflict 
	* `git pull --rebase origin master`
	* `git add .`
	* `git rebase --continue` (goes to the next commit if there's another merge conflict) 
* you only want to rebase your OWN history - don't rewrite the history of things that have already been pushed to github
* `git push --force origin master` will overwrite the github changes
* to write an extended description, don't use `-m` flag and go into vim and then add more text on the second line

## Tradecraft Patterns

#### To Dos

1. Login with Google
2. Create & Read on users
3. CRUD on Companies (inputting information)

#### To Remember

* `git pull rebase upstream master`
	* we should never have to pull from our origin

#### Links

* [Include Bootstrap](https://github.com/facebookincubator/create-react-app/issues/301) 
	* [Again](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#adding-bootstrap)

* [CSS Preprocesser](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#adding-a-css-preprocessor-sass-less-etc)
* [16 col Flex grid w/ Sass](https://github.com/roylee0704/react-flexbox-grid/issues/56)

* [React Cellblock](https://github.com/dowjones/react-cellblock)

* [Google Sign In Branding Guidelines](https://developers.google.com/identity/branding-guidelines)

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* #

