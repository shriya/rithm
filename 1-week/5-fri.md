# Friday April 28

## Warm Up
* [Repl.it hammingDistance & oneCharDifference functions](https://repl.it/student/submissions/882613)
* Things to keep in mind (my submission vs. Matt's solution):
  * Save lengths in "long" and "short" variables instead of repeating the same code twice with two different if statements

## [ES2015](https://www.rithmschool.com/courses/advanced-javascript-part-2)
* ES2015 is also called ES6 
* Before, we had ES5 

### Hoisting
* Declaration is not the same as assignment
* If you assign a variable without the `var` keyword inside of a function, it's created in the global scope
* If you assign a variable (**with** the `var` keyword) below, it's **declared** above (but assigned to `undefined` first)
* If you assign below (**without** the `var` keyword), you get a `ReferenceError`	
	
### `let` & `const`
* In ES5, we used `var` to declare all variables
* you can only declare variables once! so you **can't** do: 
	* `let myName = "Elie"`
	* `let myName = "Tim"` **type error**
* reassignment is ok though:
	* `let myName = "Elie"`
	* `myName = "Tim"`
* `const` cannot be reassigned
	* `const myLastName = "Lane"`
	* `myLastName = "Garcia"` **type error**
* `let` and `const` preserve the idea of block scope; in the following example, if we used `var` it would be global, but if we use `let`, it's scoped inside the block (inside the `for` loop)
	* also inside `if` statements or `while` loops

```
// old way; will log 5...5...5...
for (var i = 0; i < 5; i++) {
	setTimeout(function() {
		console.log(i);
	}, i*1000);
}

// new way; will log 0, 1, 2, 3, 4
for (let i = 0; i < 5; i++) {
	setTimeout(function() {
		console.log(i);
	}, i*1000);
}
```

###  template strings
```
// string concatenation

function introduce(firstName, lastName, employer, location) {
	return "Hi, my name is " + firstName + " " + lastName + ", and I work at " + employer + " in " + location + "!"; 
}

// easy to forget the spaces and +s! 
// instead, use template strings: 

function introduceNew(firstName, lastName, employer, location) {
	return `Hi, my name is ${firstName} ${lastName}, and I work at ${employer} in ${location}!`; 
}
// use backtick instead of quotes
// use ${var} to inject vars
``` 

###  default parameters
```
// old way to do default arguments
// if there's an argument value, use it, otherwise (if it's undefined or any falsey) use default
// doesn't work if you want 0s!

function add(x,y) {
	x = x || 5;
	y = y || 5;
	return x + y;
}

// new way to do it
// no longer have edge case with 0's or other falsey values

function add(x = 5, y = 5) {
	return x + y;
}
```

###  arrow functions
```
// old way to do function

function add(x,y) {
	return x + y;
}

// new way; arrow functions
// concise syntax; no function keyword, no return keyword if 1 line

add(x, y) => x + y;

// don't even need () around arguments if 1 parameter

const double = num => 2 * num;

> double(4)
>> 8

const sayHi = () => "Hi";

> sayHi() 
>> "Hi"

// if multiple lines, you need {} 
// and if arrow function sees {}, you need return keyword

const maybeSayHi = () => {
	if (Math.random() < 0.5) {
		return "Hi";
	} else {
		return "No hi for you";
	}
}

> maybeSayHi() 
>> "Hi"

> maybeSayHi() 
>> "No hi for you"
```

###  `rest` & `spread` operators
```
function showMeTheArgs() {
	return arguments;
}

>> [1, 2, 3, 4, callee: function, Symbol(Symbol.iterator): function]
// can't use array-like function on the "arguments" result because it's not a normal array
``` 
* with `rest` operator `...`, you never need to use `arguments`

```
function showMeES2015(...foo) {
	console.log(Array.isArray(foo), foo.forEach);
	return true;
}

> showMeES2015(1, 2, 3, 4)
>> true // function forEach() { [native code] } // says yes, it is an array
>> [1, 2, 3, 4] // returns the actual array of 4 values

// grab the "rest" of the arguments
function extra(num1, num2, ...nums) {
	console.log(nums);
}

> extra(1, 2, 3, 4, 5)
>> [3, 4, 5]

// gives you all of the "rest" of the args in an array
```

* `spread` operator used when calling function, not defining
* kind of the "reverse" of `spread`

```
function add(a,b,c,d) {
	return a + b + c + d;
}
> add(1,2,3,4)
>> 10

> add(...[1,2,3,4])
>> 10
// "spreads" out the array of arguments into the individual arguments
```
### object shorthand notation
#### variable shorthand
```
var firstName = "Matt";
var lastName = "Lane";

// old way
var person = {
	firstName: firstName,
	lastName: lastName
}

// new way
// don't need to duplicate names and values
// makes name of key same as name of var
// makes value same as value of var
var personES2015 = {firstName, lastName} 
```

#### function shorthand
```
var firstName = "Matt";
var lastName = "Lane";

// old way
var person = {
	firstName: firstName,
	lastName: lastName,
	sayHi: function() {
		return "Hi, I'm " + firstName + " " + lastName;
	}
}

> person.sayHi();

// new way
// don't need to duplicate names and values
var personES2015 = {
	firstName,
	lastName
	sayHi() {
		return `Hi, I'm ${firstName} ${lastName}`;
	}	
}
```

#### use variables as names in objects
```
var name = "Shriya"
var obj = {}
obj = {[name]: "my name"}

>> Object {Shriya: "my name"}
```

###  destructuring assignments
```
var obj = {a:1, b:2, c:3}

// instead of 
var a = obj.a;
var b = obj.b;
var c = obj.c;

// we can do
var {a, b, c} = obj;

// also works with a subset of all the keys in that object
var {a, b} = obj;
```

```
var arr = ["up", "down", "right", "left"]

var[u, d, r, l] = arr

// assigns u to "up", etc.
```

### swap

```
var a = 5;
var b = "hello";

swap (a,b);

// swaps their values
```

```
// how to swap values with destructuring: 

var a = 1;
var b = 2;

// assigns b to value of a
// and a to value of b

[b,a] = [a,b]
```

## Intermediate JS Part 2

#### [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) 
* **Hyper Text Transfer Protocol**
* allows _client_ to get data from the _server_ or set data on the server
* _request-response_ protocol
* _client_ submits an HTTP _request_ to the server, _server_ provides a _response_ to the client containing information about the request and the content requested
* an _application layer protocol_ designed within the framework of the Internet protocol suite; presumes an underlying and reliable _transport layer protocol_, such a TCP
* HTTP is a _stateless_ protocol; each command is executed independently without knowledge of the commands that came before it
* HTTP _status codes_ are error messages; ex. _404 File Not Found_, which means that the _server_ can't find the file you requested
* [More Status Codes](http://www.webopedia.com/quick_ref/error.asp)

#### [URL](https://en.wikipedia.org/wiki/URL)
* **Uniform Resource Locator**
* also known as a _web address_ 
* reference to a _web resource_ that specifies a location on a _computer network_ and a mechanism for retrieving it
* specific type of _[URI (Uniform Resource Identifier)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier)_ 
* `http://www.example.com` is a URL, but `www.example.com` is not; URLs specify the means to access the indicated resource via a protocol or other access mechanism
* URLs are used to reference _web pages_ (`http`), _file transfer_ (`ftp`), _email_ (`mailto`), and more.
* web browsers display the URL of a web page in the address bar with the form `http://www.example.com/index.html` indicating the _protocol_ (`http`), the _hostname_ (`www.example.com`), and a _file name_ (`index.html`)
* generic URI syntax: ` scheme:[//[user[:password]@]host[:port]][/path][?query][#fragment]`

#### [TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
* **Transmission Control Protocol**
* "makes sure data is in the right order and none of it is missing"
* one of the main protocols of the _[Internet Protocol Suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)_
* part of the popular **TCP/IP** combination used by the Internet
* helps control traffic on the internet so it doesn't get overloaded
* provides reliable, ordered, and error-checked delivery of a stream of bytes ([octets](https://en.wikipedia.org/wiki/Octet_(computing))) between applications running on hosts communicating by an IP network

#### [IP](https://en.wikipedia.org/wiki/Internet_Protocol)
* **Internet Protocol**
* "makes sure data gets to the right place"
* one of the main protocols of the _[Internet Protocol Suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)_
* IPv4 address has 4 #s between 0-255 (256^4 devices ==> 4 bil)
	* 0.0.0.0 to 255.255.255.255
* now IPv6 addresses

#### [DNS](https://en.wikipedia.org/wiki/Domain_Name_System)
* **Domain Name System**
* hierarchical decentralized naming system that associates domain names to numerical IP addresses
* use "phone book" analogy (human-readable names rather than IP address which is list of numbers)

#### Request
* Part of _Request/Response Cycle_
* client makes a request
* part of HTTP is request/response cycle
* curl allows you to make a request from the command line

#### Response
* Part of _Request/Response Cycle_
* server answers to browser; status code & body (body is the HTML document)

#### Header
* part of HTTP requests; contains additional info about request or response - ex. cookies, info about server 
* meta-information separate from actual request or response
* can see response headers in Network tab of Chrome DevTools

#### AJAX
* **Asynchrynous Javascript And XML**
* many web techniques allowing web pages or apps to dynamically change content without refreshing the page (ex. Gmail, Facebook, Twitter)
* AJAX requests (on a timer), then you get a response -- so you don't have to refresh and send a new request (with page refresh)
* Outdated abbreviation; now for the most part, we get JSON data rather than XML data

#### Status Code
* Status Codes are HTTP Error Messages
* Success (200s), redirect (300s), client-side errors (400s) -- ex. 404 not found, server-side errors (500s)
* [status cats](https://http.cat/)

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* Refactor old assignments to fix Elie's comments on my old Github pull request!
* Refactor `Guess the Password`
* Intermediate JS Part 2 - super thoroughly!!! Do this weekend!!!
* [Internet in 5 Mins](https://www.youtube.com/watch?v=7_LPdttKXPc)
* [Code.org Internet videos](https://www.youtube.com/watch?v=ZhEf7e4kopM&index=1&list=PLzdnOPI1iJNfMRZm5DDxco3UdsFegvuB7)
* [What happens when](https://github.com/alex/what-happens-when)

## Coming up this week

* 




