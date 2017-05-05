# Wednesday May 3

## Warm Up

* [Count Pairs](https://repl.it/student/submissions/912810)
* Three ways to solve:
	* "Brute force" method; nested for loops
	* Space efficient way; two pointers
		* Time Complexity - O(n * log(n))
		* Space Complexity - O(1)
	* Time efficient way; put values in object then test if key (n - i) exists, for each key i - lookup is constant (searching better in an object than an array). if found, increment counter and remove them.
		* Time Complexity - O(n)
		* Space Complexity - O(n)
* New ES2015 data structure: [Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

## OOP in JS

```
var house1 = {
	numBed: 1,
	numBath: 1
}

var house2 = {
	numBed: 2,
	numBath: 3
}
```

* Everything we instantiate from a class is an object
* JS is not an object-oriented language; not built-in

## "this" keyword in Javascript

* keyword `this` is the thing that allows us to "pretend" that JS is Object-Oriented
* the value of `this` is determined when a function is run
* When we create a function, two special keywords are created - `this` and `arguments` 
* In the browser, the `window` is the "global object"
* everything you make is part of the `window` object

* 4 Rules to determine value of keyword `this`: 

1) Global
2) Implicit
3) Explicit
4) `new`

Lower on this list override higher on this list!

* "execution context" is the context in which a function is run

### 1) 
* `this` "in the world" - refers to the global object
* If `this` is inside a function, **but** that function is not inside an object, `this` still refers to the global object (`window`)
* In strict mode (type `"use strict"`), the keyword `this` is `undefined` - so you can't set properties on it
* [more about strict mode](http://cjihrig.com/blog/javascripts-strict-mode-and-why-you-should-use-it/) -- [more](http://stackoverflow.com/questions/8651415/what-is-strict-mode-and-how-is-it-used) -- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)

### 2)
* When `this` is used in an function, **and** the function is inside an object, then `this` refers to the object
* Only reassigned when a function is run!! Can't just use `this` in an object; there must be a function that is running
* Object it refers to is **closest** parent

### 3)
* Explicitly setting: `call`, `apply`, and `bind` 
* Only `functions` have those three keywords
* You *cannot* invoke call, apply, or bind on anything else (numbers, strings, arrays, etc)
* Changes the value of `this` 
* First parameter of all of them is the same; what you would like the value of the keyword `this` to be
* `thisArg` is first argument 
* `call` & `apply` both invoke the function immediately
* with `call`, comma-separate all arguments; first one is `thisArg`, next are all remaining args
* with `array`, second argument is an array of all values (ES5 version of `spread` operator)

#### [call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)

```
var student1 = {
	firstName: "Shriya",
	faveColor: "Teal",
	sayHi: function() {
		return "Hello " + this.firstName + " whose fave color is " + this.faveColor;
	}
}

var student2 = {
	firstName: "Tobi",
	faveColor: "Salmon"
}

// invoke function from student1 with data from student2
student1.sayHi.call(student2)
```

#### check out how to spread values with [`apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

```
var arr = [1,2,3,4,5]
Math.max(...arr) === Math.max.apply(this, arr)
returns 5
```

#### [spread out values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator) -- [rest](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters) -- [more info](https://rainsoft.io/how-three-dots-changed-javascript/)
```
var arr = [[1,2,3,4,5]];
var arr2 = [6,7,8];

[].concat(...arr, arr2);
// or
[...arr[0], ...arr2]

// how did we do it before spread operator?
// either of the following work:

arr2.concat.apply(arr[0], arr2);
// or
[].concat.apply(arr[0], arr2);

// ^^ first thing doesn't matter; just need array so it has the function concat

```

#### [`bind` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)

* `bind` also takes in `thisArg` and then comma-separated values (as many args as you want/need, like `call`) 
* **but** -- bind returns to you a "partially applied" function -- value of keyword `this` is bound
* you can then -- at any point in time -- execute that function
* **partial application** is the idea of a function that can be called multiple times, until all of its arguments have been put in
* so you can use bind with only some of the argument values

* functions have a length property; this is currying 

```
function foo (a,b,c) {
	return arguments.length
}

foo(1)
>> 1 // arguments at time of invocation

foo.length 
>> 3
```

```
// try our own implementation of bind
function bind(fn, thisArg, ...args1) {
    return function(...args2) {
        var args = args1.concat(args2);
        return fn.apply(thisArg, args);   
    }
}

function add(a,b,c) {
    return a+b+c;
}

bind(add,this,1,2,3)()

bind(add,this,1,2)(3)

bind(add,this,1)(2,3)

bind(add,this)(1,2,3)

// what if we did it in ES5? Need to use keyword arguments
function bind(fn, thisArg) {
	var outerArgs = [].slice.call(arguments, 2);
	return function() {
		var innerArgs = [].slice.call(arguments);
		return fn.apply(thisArg, outerArgs.concat(innerArgs));
	}
}
```

* put potentially unknown arguments at the end of the argument list when defining the function, so that you can update it later

### 4) 

* functions which return some kind of object
* we're trying to get closer and closer to creating classes
* Constructor function - capitalize first letter: 

```
function Person(firstName, lastName) {
	this.firstName = firstName;
	this.lastName = lastName;
}

new Person("Shriya","Nevatia);
>> returns an Object called "Person" with two keys & values
```

#### `new` keyword
* creates an empty object {}
* sets the keyword `this` to be that empty object
* adds a `return this;`
* creates a link

* Only use `new` to invoke functions; **not** when creating them (defining functions)
* `new` overwrites a primitive (ex. if you accidentally return "thing"), but it won't overwrite an object (ex. an array) -- so don't return anything in a constructor function

* **there is NO built-in idea of classes in JS; constructor functions are the closest thing JS has to classes**

```
function Person(firstName, lastName, favoriteColor){
    this.firstName = firstName;
    this.lastName = lastName;
    this.favoriteColor = favoriteColor;
}

function Student(firstName, lastName, favoriteColor) {
    Person.apply(this, arguments);
}

new Student();
```

## Prototypes & Constructors

* All functions have a property called `.prototype`
* For function `Person`, there is an Object on it called `Person.prototype`
* Objects have a property on it called `.constructor` 
* `_ _ proto _ _` ("dunder proto" - double underscore proto) --> `__proto__`
* fourth thing the `new` keyword does is - establish a `link` between Object created with `new` keyword and the `prototype` property of the `constructor` function
* There is **no connection** between the function (constructor) that creates a class, and an instance of that class
* To look up methods & properties, an instance of the object ("Matt") uses `__proto__` to see if that method/property is on `Person.prototype`, then goes up chain to `Object.prototype` to see that yes it has that function (ex. `toString`) 
* One level up `Object.prototype` is `null` (`__proto__` of `Object.prototype` is `null`)
* `Person.prototype.constructor === Person`
* Only functions have the `prototype` property
* `Object` is a constructor function for making new objects
* `Array` is a constructor function for making new arrays

```
function Person(firstName, lastName, favoriteColor){
    this.firstName = firstName;
    this.lastName = lastName;
    this.favoriteColor = favoriteColor;
}

Person.prototype.constructor === Person
// true

var shriya = new Person("s","n","teal");

shriya.__proto__ === Person.prototype
// true

shriya.__proto__.__proto__ === Object.prototype
// true

shriya.__proto__.__proto__.__proto__ === null
// true

shriya.toString() === shriya.__proto__.__proto__.toString()
// true 
// this is abstracted away from us

// we should put functions on the Person.prototype instead of Person
Person.prototype.fullName = function() {
	return `${this.firstName} ${this.lastName}`;
}

shriya.fullName();
// returns "Shriya Nevatia";

// but now fullName is in shriya.__proto__, not in the object shriya
// more efficient to put methods in the prototype because they're shared & defined once
// anything you make in the prototype is shared in every object that has a link to it; will be MODIFIED for all other objects, if one object modifies it!!! 
// define **unique** properties in the constructor function
```

************************************

## Questions 

* 

## Ideas & Notes

* Mergesort & Quicksort are `O(n log n)` (fastest sorting)
* `Symbol.iterator` is a special method that's already implemented for you in havascript (if you look at `__proto__` in an array in the chrome console) 
	* `for...of` loop

```
for (let val of arr) {
	console.log(val);
}
```

## To Do

* [Iterable Protocol & Iterator Protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
* [Iterators & Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators)
* [Symbol.iterator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator)
* [for...of statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
* [Imperative vs. Declarative Programming](https://tylermcginnis.com/imperative-vs-declarative-programming/)

* Watch tons of [JS Videos on YouTube](https://www.youtube.com/channel/UCO1cgjhGzsSYb1rsB4bFe4Q/playlists)

* [Currying](https://medium.com/@kbrainwave/currying-in-javascript-ce6da2d324fe) / [More](https://medium.com/@kevincennis/currying-in-javascript-c66080543528) / [And More](https://www.sitepoint.com/currying-in-functional-javascript/) / [Even more](http://www.crockford.com/javascript/www_svendtofte_com/code/curried_javascript/index.html) / [Ok enough](http://blog.carbonfive.com/2015/01/14/gettin-freaky-functional-wcurried-javascript/)

* [console.dir()](https://developer.mozilla.org/en-US/docs/Web/API/Console/dir) -- [more info](http://stackoverflow.com/questions/11954152/whats-the-difference-between-console-dir-and-console-log)

## Coming up this week

* today: `new`, OOP
* Thurs & Fri - more OOP - games w/ Canvas & OOP
* Friday - assessment: review of past couple of weeks, see how well we taught - similar to warm-ups but with more time (2-2.5 hours)


