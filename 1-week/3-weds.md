# Wednesday April 26

## Warm Up

* ### [Snail Sort](https://www.codewars.com/kata/snail/train/javascript) 
	* `shift` (remove top row) -- or `concat`: 
	  * `[].concat([1, 2])` ==> `[1, 2]` 
	  * `[].push([1, 2])` ==> `[[1, 2]]` -- we don't want this extra dimension
	* `pop` off last elements of all arrays
	* `pop` off last element until final row empty, or reverse row then concat
	* `shift` (removing first element of remaining arrays -- starting a bottom "row")
	  * once it's empty, you won't be able to remove elements anymore (so you'll know to stop)
	  * once you have `undefined`, you can return the results array

* ### Array Methods review

  * **unshift** - adds to front, returns new length of array
  
  * **shift** - removes from front, returns item removed
     
  * **push** - adds to back, returns new length of array
  
  * **pop** - removes from end, returns item removes  
   
  * **slice** - doesn't mutate array; creates new array with sub-array from original (if only one arg, does index argument to end)
      * to make a copy of an array: `copy = array.slice()` (slice with no arguments)
      
  * **splice** - returns array of what was removed; mutates original
  
  * **concat** - returns a new array; does not mutuate original array
  
  * **reverse** - _does_ mutate original array; returns that array

## More Array Methods

#### indexOf
  * returns the index of a value you pass in 
  * `[1, 2, 3].indexOf(2);` ==> `1`
  * Way to search for values without a loop
  * Find out what's not in the array; returns `-1`
  * `O(n)` operation (linear search) -- be careful about putting this INSIDE a `for` loop
  * if repeats, only gives you the first one

#### includes
  * `[1, 2, 3].includes(7);` ==> `false`
  * returns `true` or `false` (instead of -1) 
  * newer to JS
  * also `O(n)`

#### lastIndexOf
  * searches from the end of the array for a value, and gets the index of that one
  * rather than beginning
  * `[1, 2, 3, 2, 4].lastIndexOf(2);` ==> `3`

#### sort 
  * if you sort on mixed types, it won't be what you expect
  * if you have negative values, it will sort in a weird way, i.e. `[-1, -2, -3, 1, 2, 3]`

#### forEach
  * Could do something to each item in an array in an **Imperative** way by using a for loop or some other loop
  * Using `forEach` is the **Declarative** approach (bc loop is under the hood)
  * Always returns undefined; even if callback has "return" in it

```
var arr = [1, 2, 3, 4, 5];
arr.forEach(function(val) {
  console.log(val)
})
```

#### map 
  * always returns an array of same exact length as original array
  * makes new array of same size, iterate and run callback for each value, push each into array, and return

```
// Double each value in an array
var arr = [1, 2, 3, 4, 5];

// Imperative Approach
var newArr = [];

for (var i = 0; i < arr.length; i++) {
    newArr[i] = arr[i] * 2;
}
return newArr;

// Declarative Approach
arr.map(function(value, index, array) {
	return value * 2;
})
```

#### filter
  * Callback function in filter must return `true` or `false`
  * Don't use `if` statements in filter (that's the whole point)
  * `filter` returns an array (same or different length)

~~~~
// Return array of only odd values
var arr = [1, 2, 3, 4, 5, 6, 7, 8];

arr.filter(function(value) {
	return (value % 2 === 1);
})
~~~~

#### every  
  * without the return outside of the callback, this returns `undefined`
  * callback must return boolean
  
~~~~
var arr = [1, 2, 3, 4];
function isGreaterThanThree() {
	return arr.every(function(val) {
		return val > 3;
	});
}
// false
~~~~

#### some
  * returns `true` if some values pass bool operation in callback
  * returns `false` if none do

~~~~
var arr = [1, 2, 3, 4];
function someGreaterThanThree() {
	return arr.some(function(val) {
		return val > 3;
	});
}
// true
~~~~

#### find
  * return the item you were trying to find
  
~~~~
var arr =[{name: "Elie"}, {name: "Tim"}, {name: "Matt"}];

function findMatt() {
    return arr.find(function(val) {
	   return val.name === "Matt";
    })
} 

findMatt();
~~~~

#### findIndex
  * has a callback function; this is difference between `indexOf` and `findIndex` 

#### every

#### reduce


## Imperative vs. Declarative

* Imperative: start at Rithm school, then take a left, walk 3 blocks, take a right, etc...then end at 1170 Wash

  * explains every step

* Declarative: start at Rithm school, go to 1170 Wash 

  * assumes you know how to meet the goal based on initial state










************************************

## Questions 

* 

## Ideas & Notes

* Binary search is `O(log n)` but it has to be sorted

* 

## To Do

* Double values in an array imperatively, declaratively, and recursively

* Return array with only odd values imperatively, declaratively, and recursively

* 

## Coming up this week

* Outco happy hour this Fri evening

* React.JS 10am-4pm Saturday (kind of advanced for us right now)

* OOP 10am-4pm Sunday (preview of what we'll do next week)

* Next week - make HN Clone, build some games, last week of client-side JS (HTML, CSS, JS)

* 













