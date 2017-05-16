# Tues May 16

## Warm Up

* [`areThereDuplicates() and addCommas()`](https://repl.it/student/submissions/992834)

## More Flask
 
### Requirements

* `pip freeze` inside virtual env in terminal; see all dependencies
* funnel into a file (two >> for "append", one > to "overwrite") `pip freeze >> requirements.txt`
* every time you install a new dependency, write it to `requirements.txt`
* to reinstall all the dependencies, (ex. when you run someone else's app) they run `pip install -r requirements.txt` to get all the required dependencies


### Redirects

* `import redirect`
* redirecting allows you to reduce code duplication
* `werkzeug` is a dependency of flask that does routing
* 300 status code is a redirect
* redirect takes location as an argument; location is a string - it's also the header of the place to go
* `response.headers['location'] = location`
* ^ setting property in headers dictionary to be the value of the location that we passed in!! 
* `redirect(location, code, Response)`
* redirect defaults to status code `302`

### url_for

* google for what we're looking for to find function definition
* this one is in flask, in helpers.py
* `def url_for(endpoint, **values)`
* (the values are kwargs; keyword arguments)
* `return redirect(url_for('first', name="Elie"))`
* the endpoint is the name of a function; not the name of the route
* error handling!!! check the stack trace, look for our own file (towards the bottom), check the console - type in the PIN - and see where you went wrong 

### Getting data from a user

* 

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* Get better at thinking about rest operator and spread operator
* Get better at 2-pointer problems; practice more

## Coming up this week

* 

