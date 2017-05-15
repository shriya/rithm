# Monday May 15

## Warm Up

* [Count Unique Values - Repl.it - Javscript](https://repl.it/student/submissions/985276)

## Python Flask Intro - Server-Side Applications

* making virtual environments
* requests & responses from server to client
* HTTP requests have GET and POST -- a GET request is idempotent 
* idempotent: "clients can make that same call repeatedly while producing the same result"
* every time you make a GET request, you always get back the same response
* server-side applications

## Virtual environments 

* get out: `deactivate`
* get back in: `workon first-flask-app`

## First Flask App

```
from flask import Flask
app = Flask(__name__)

# when someone goes to the root route '/'

@app.route('/', methods=["GET", "POST"])

# i want to run a function

def root(): 
    return "Hello World!!!!"
    # the returned value from the function
    # will be my response


@app.route('/person')
def person(): 
    return """
        <p>Whoa</p>
        <h1>Hello</h1>
        <h1>sup</h1>
    """

    # create a rout for '/person'
    # when a GET request is made - return the value "Hello!"

if __name__ == '__main__':
    app.run(debug=True, port=3000)
```

************************************

## Questions 

* 

## Ideas & Notes

* [Random Python Codewars Problem](https://www.codewars.com/kata/convert-color-image-to-greyscale/train/python)

## To Do

* Add more to D3 project
	* [HTML Color Codes](http://htmlcolorcodes.com/)
	* [Visualization Project](https://github.com/rithmschool/visualization_project)
	* [Intermediate D3](https://github.com/rithmschool/intermediate_javascript/blob/master/unit-02/10-intermediate-d3.md)
	* [Intro to D3](https://github.com/rithmschool/intro_to_d3)
	* [D3 Transitions](https://github.com/d3/d3-transition)
	* [Goodreads CS Shelf](https://www.goodreads.com/shelf/show/computer-science)
	* [HTML Button Group](https://www.w3schools.com/howto/howto_css_button_group.asp)
	* [D3 Grid Lines](https://bl.ocks.org/d3noob/c506ac45617cf9ed39337f99f8511218)
	* [D3 Tick Format](https://bl.ocks.org/mbostock/9764126)
	* [CSV Reading & Writing in Python](https://docs.python.org/dev/library/csv.html#csv.writer)
	* [Python writing .csv files](http://stackoverflow.com/questions/15727084/writing-csv-files-from-for-loops-and-lists)
* HN AJAX
	* [Github Repo](https://github.com/HackerNews/API)
	* [AJAX w/ jQuery exercise](https://github.com/rithmschool/intermediate_javascript_exercises/tree/master/ajax_with_jquery_exercise)
* Left off
	* [left off in JS](https://www.rithmschool.com/courses/intermediate-javascript-part-2/how-the-web-works-http-rest)
	* [left off in python](https://www.rithmschool.com/courses/python-fundamentals-part-1/python-functions-exercises)		 

## Coming up this week

* 

