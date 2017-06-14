# Friday May 19

## Warm Up

* [averagePair() and sameFrequency()](https://repl.it/student/submissions/1013205)
* for two-pointer solutions, make sure you're hitting every possible pair
* REMEMBER THAN O(n) + O(n) === 2 * O(n) === O(n)!!! IT'S NOT N^2!! 

## [Forms with Flask WTF](https://github.com/rithmschool/python_curriculum/blob/c451fef4dcd7ea000c9dd5b4d73005df88aeb46e/Unit-01/09-forms.md)

* security concerns for forms if you have them in pure HTML
* also want to have validation; ex. name length, valid email, etc.

### CSRF

* CSRF - [Cross-Site Request Forgery](https://en.wikipedia.org/wiki/Cross-site_request_forgery) - use CSRF token when submitting a form; server validates that you are sending a valid token
* Any form we generate has a hidden token
* CSRF is making a request to the server that the user doesn't want or realize they're making; ex. adding unwanted DVD to netflix queue
* hijacking user & making request
* Need secret key to generate the token
* To generate the secret key, need to create an environment variable
* bad way to do it: `app.config['SECRET_KEY'] = 'shhhh'` 
* postactivate is a file that's run after virtual environment activated; can put secret key in there

### Forms & Form Hijacking

* when you make a GET request, `form.data` is empty because `request.form` is an `ImmutableMultiDict()` 
* once you make the POST request, then `form.data` is populated with the user's input data
* `form.errors` will show all errors; gives you built-in error messages based on field types! 
* form has all data user has typed in because we pass `form` into the `render_template('signup.html', form=form)` return statement in `app.py`
* FlaskWTF doesn't allow you to hijack form with keys that the class isn't expecting!! So you can't type in `is_admin` and set it

### Flash Messages

* show up on a page, then when you move to diff page - gone
* need to put `get_flashed_messages()` in html files - comes with Flask 

### Heroku Stuff

* heroku run ipython
* heroku pg:psql

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up next week

* 

