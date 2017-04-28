# Friday April 28

## Warm Up
* [Repl.it hammingDistance & oneCharDifference functions](https://repl.it/student/submissions/882613)
* Things to keep in mind (my submission vs. Matt's solution):
  * Save lengths in "long" and "short" variables instead of repeating the same code twice with two different if statements

## (ES2015)[https://www.rithmschool.com/courses/advanced-javascript-part-2]
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

###  destructuring assignments
* 




************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* Elie comments on Github commit 
* 

## Coming up this week

* 




