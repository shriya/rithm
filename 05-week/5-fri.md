# Friday May 26

## Warm Up

* [Index and BST problem](https://repl.it/student/submissions/1046818)
* Remember that binary search can be done WITHOUT a binary search TREE!! -- you can just search through an array in halves in order to get an O(log n) algorithm.

## Warbler

* continuing [Warbler project](https://github.com/rithmschool/warbler)

## Cookies

* a cookie is a key and a value that a browser can set or a server can set; typically for authentication, the server is setting it
* logins on sites today are typically done with cookies
* browser makes a GET request to get a form from our Flask app
* the format of a GET request (or any HTTP request) has the verb (GET) and the route (/users/signup), then the Headers (Cookies, length of request, content type, etc.), then the newline, then the body (data -- optional -- for a GET there is typically no data in the body)
* response we get back from Flask app to browser -- Status (ex. 200), Headers (Set-Cookie, content type, length of response, etc), space, Body (actual HTML itself).
* the browser gets other data beyond the above HTML -- like the images, Javascript, etc. -- via **more** GET requests
* flask_login -- the server decrypts our data and authenticates that the user id exists in our database
* we're not just setting one cookie for authentication; we're using the Session - which is a Cookie. the Session is a dictionary full of keys and values that we are encrypting or decrypting.
* one site cannot access another site's cookies; if i'm on warbler.com I can only get cookies from warbler.com
* the browser saves all the cookies of all the sites that you've visited until they've been cleared

## CSRF & CSRF Attacks

* always have to CSRF-protect anything changing state (POST, PATCH, DELETE) 
* GET requests must be idempotent so should NOT have to be protected because they should NOT modify anything on the server
* CSRF protection means that the **server** creates forms that have a csrf token
* `form.validate()` checks that all form inputs are valid and that the csrf tokens match
* "Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated. CSRF attacks specifically target state-changing requests, not theft of data, since the attacker has no way to see the response to the forged request."

## Assessment Notes

* 300 status codes are redirects
* Response header location tells the browser where to redirect to if there's a redirect
* the salt is a string added to the hash to add randomness - it makes reverse-engineering the hash harder 
* 

## Next Week's Web Project

* [Full stack project guidelines!](https://github.com/rithmschool/fullstack_project)


************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

