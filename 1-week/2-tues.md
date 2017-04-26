# Tuesday April 25

## Warm Ups

[Codewars Problem 1: Dictionary from two lists](https://www.codewars.com/kata/5533c2a50c4fea6832000101)

* Don't get super hung up on doing the most "fancy" technique; ex. reduce can be used, but for loop works

* Write or think about sample input & sample output before writing anything, so you know what to check

* Think about all the edge cases first; ask a lot of clarifying questions

[Codewars Problem 2: Valid Parentheses](https://www.codewars.com/kata/52774a314c2333f0a7000688)

* Think about some edge cases -- starting with a close paren, having an odd # of parens

* For this one, I used a stack (pushing for "(" and popping for ")") rather than a counter (+1 and -1) so that I checked to make sure I never popped from an empty stack (but could also check to make sure I didn't dip below 0)

## Intro to Recursion

* An alternative to iteration; a function that calls itself 

* Terminal command for removing **recursively**: `rm -r mydir` 

* Document data structure - upside-down tree; also in HTML 

  * to check HTML tree for an `id="me"`

  * check html; is this `id="me"`?

  * if no, does this have children?

  * if yes, traverse first child

  * repeat, then bump up to other child when you hit leaf (depth-first)

  * --> can also do breadth-first search

* If you have an infinitely recursive function, you get a **stack overflow** (JS: Range Error: Maximum call size exceeded)

* So you need a **base case**! This tells you when to stop

* Our input has to change with each recursive call (often entire scope changes)

## HTTP

* Hyper Text Transfer Protocal

* Sending data from client to server - must be text 

  * HTML

  * XML

  * JSON (Javascript Object Notation) _a big JS object stringified_

* JSON.stringify(anything);

  * how does this work? recursively!

  * the base case is "when the loop is done" i.e. when you run out of keys 

  * JSON syntax is a little different than literal JS object syntax, so you must go through it recursively

    * functions, undefined, null, bools...all end up different

## Recursion Practice

### `countDown` example

~~~~
// write a function called countDown
    // this function accepts 1 parameter, a number
    // it will console.log that number minus 1
    // until we reach 0

function countDown(num) {
    if (num === 0) {
        return;
    }
    console.log(num);
    countDown(num - 1);
}

countDown(5);
~~~~

* push 5, 4, 3, 2, 1 on the call stack - then pop all at the end (they've already console.logged)

### `factorial` example

* 4! = 4 * 3! 
* 3! = 3 * 2!
* 2! = 2 * 1!
* 1! = 1 (base case)

* return the result of 1! to 2, then 2! to 3, then 3! to 4, then you have 4! (original goal)

~~~~
// function factorial

function factorial(num) {
    if (num === 1) {
        return 1;
    } 
    return num * factorial(num - 1);
}

factorial(4);
~~~~

### `range` example

~~~~
// function range 

function range(num) {
    if (num === 1) {
        return 1;
    }
    return num + range(num - 1);
}

range(3);
range(8); // equivalent to (n(n+1)/2)
~~~~

### `power` example

~~~~
// function power

function power(base, exp) {
    if (exp === 0) {
        return 1;
    }
    return base * power(base, exp - 1);
}

power(2, 4);
~~~~

### `fib` example

~~~~
// function fib

function fib(n) {
    if (n <= 2) {
        return 1;
    }
    return fib (n - 1) + fib (n - 2);
}

fib(6);
~~~~

* This is O(2<sup>n</sup>) -- *super* expensive; fib(50) will crash computer

* When you break a problem down into smaller sub-problems - dynamic programming

  * Can go top-down -- memoization (solving problems by breaking into smaller sub-problems)

  * Can go bottom-up -- tabulation (work upwards towars calculating)

* We can bring it to O(n)

### `palindrome` example

~~~~
function palindrome(str) {
    if (str.length <= 1) {
        return true;
    } else if (str[0] !== str[str.length-1]) {
        return false;
    } else {
        palindrome(str.slice(1, -1));
    } 
    return true;
}

palindrome("tacocat");
~~~~

### `every` function 

* function called on an array; check if every element in the array meets some condition. 

* the condition is a callback function

* this already exists in JS but we were writing our own implementation

* Normal every function: 

~~~~
[1, 2, 3, 4].every(function (value, index, array) {
	return value > 3;
});

// false
~~~~

* Mine:

~~~~
function everyFunc(arr, cond) {
    if (arr.length <= 0) {
        return true;
    } else if (!cond(arr[0])) {
        return false;
    } else {
        return everyFunc(arr.slice(1), cond);
    }
}

everyFunc([1, 2, 3], function(x) {
    return x > 0;
});

everyFunc([1, 2, 3], function(x) {
    return x > 6;
});
~~~~

## Instructor Solutions from Elie

~~~~
function countDown(num){
    if(num === 0) return;
    console.log(num)
    countDown(num-1)
}

function factorial(x){
   if (x === 1 ) return 1;
   return x * factorial(x-1);
}

function recursiveRange(x){
   if (x === 0 ) return 0;
   return x + recursiveRange(x-1);
}

function power(base, exponent){
    if(exponent === 0) return 1;
    return base * power(base,exponent-1);
}

function fib(n){
    if (n <= 2) return 1;
    return fib(n-1) + fib(n-2);
}

function reverse(str){
    if(str.length <= 1) return str;
    return reverse(str.slice(1)) + str[0];
//     return str[str.length-1] + reverse(str.slice(0,-1))
}

function isPalendrome(str){
    if(str.length === 1) return true;
    if(str.length === 2) return str[0] === str[1];
    if(str[0] === str.slice(-1)) return isPalendrome(str.slice(1,-1))
    return false;
}
~~~~

## Helper Method Recursion

~~~~
// remember a variable through each recursive call 

function toughRecursiveProblem(input){
    
    var arrayToRemember = [];
    
    function helperFunction(){
        arrayToRemeber.push('whatever');
        return helperFunction(input);
    }

    helperFunction(input);

    return arrayToRemember;
}
~~~~

************************************

## Questions 

* 

## Ideas & Notes

* Cmd + D to find the next instance of word your cursor is on

* Shift + Tab to do left / reverse tab

## To Do

* Outco interview - get comfortable with level 5 & 6 problems on Codewars

* Interviews in general - get comfortable with level 3 & 4 problems - good shape!!

* [MPJ Videos - Functions, Recursion, Programming](https://www.youtube.com/channel/UCO1cgjhGzsSYb1rsB4bFe4Q)

* Recursively reverse a string

* O(n) algorithm for fibnnoaci sequence

* Chrome console -- set breakpoints, put functions in "Watch", then click through the call stack

* 

## Coming up this week

* Tomorrow - map, for each, etc. lots of JS functions

* Thurs - DOM Manipulation, HTML Canvas











