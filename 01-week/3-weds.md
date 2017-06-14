# Wednesday April 26

## Warm Up

* ### [Snail Sort on Codewars](https://www.codewars.com/kata/snail/train/javascript) 
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
  * you can run `includes` on a string, too!!

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
  * `filter` returns an **array** (same or different length)

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

#### reduce

~~~~
["Elie", "Matt", "Tim", "Janey"].reduce(function(previousValue, nextValue) {
	return previousValue;
})
// "Tim"
~~~~

* `accumulator` is also called `previousValue`
* `curr` is also called `nextVal`

* `reduce` does NOT go in order -- whatever you return from the callback becomes the `previousValue` the next time
* ONLY the `nextValue` is going to iterate through the array

* `reduce` itself returns the final value of `previousValue`

* Can pass a second argument to reduce; think of this as "initial `previousValue`"

~~~~
["Elie", "Matt", "Tim", "Janey"].reduce(function(previousValue, nextValue) {
	return previousValue + " " + nextValue;
}, "The Rithm Team Includes: ")
// "The Rithm Team Includes: Elie Matt Time Janey"
~~~~

* think of **reducing an array into something else**; ex. reduce array into string
* good for summing up numbers in an array, or building up a concatenated string

* if you don't `return` anything from the callback function, `previousValue` becomes `undefined`

#### every

## Imperative vs. Declarative

* Imperative: start at Rithm school, then take a left, walk 3 blocks, take a right, etc...then end at 1170 Wash
  * explains every step
* Declarative: start at Rithm school, go to 1170 Wash 
  * assumes you know how to meet the goal based on initial state

## Binary Search
* `[1, 2, 3, 4, 5, 6, 7]`
* `function binarySearch(arr, val);`
* Find the midpoint of the Math.floor(arr.length/2);
* Test if value is equal to this value (or the one to the right);
  * `val === arr[middle]  return middle`
  * `val < arr[middle]`  call again on left half
  * `val > arr[middle]`  call again on right half
  * if not found, `return -1`
* This loses the indices, so instead:
  * `function binarySearch(arr, val, start, end) {}`
  * `start = start || 0` first time you call it, start is undefined; undefined is falsey so first time, skips to 0
  * `end = end || array.length` first time you call it, end is undefined; undefined in falsey so first time, skips to array.length - 1
  * **short circuiting** - assigning something to `(thing || otherThing)` - assigning conditionally 
  * **JS specific thing** - that you can define the function with 4 arguments, but call it with only 2 
  * `binarySearch(arr, val)`
* Always need some midpoint 
  * `var mid = Math.floor((start + end) / 2);`

~~~~
function binarySearch(arr, val, start, end) {
	start = start || 0;
	end = end || arr.length;
	var mid = Math.floor((start+end)/2);
	if(arr[mid] === val) return mid;
	if(arr[mid] < val) {
		binarySearch(arr, val, mid+1, end);
	}
	if(arr[mid] > val) {
		binarySearch(arr, val, start, mid-1);
	}
	return -1;
}
~~~~

## Vowel Count

~~~~
function vowelCount(str) {
	var newObj = {}; 
	var vowels = "aeoiu";
	for (var i = 0; i < str.length; i++) {
		if(str[i] in newObj) {
			newObj[str[i]]++;
		} else {
			newObj[str[i]] = 1;
		}
	}
}
~~~~

* **The following doesn't work yet** 

~~~~
function vowelCount(str) {
	var newObj = {}; 
	var vowels = "aeoiu";
	for (var i = 0; i < str.length; i++) {
		// short circuiting answer
		if () {
			newObj[str[i]] = (newObj[str[i]] || 0) + 1; 
			// finds first truthy thing // otherwise if all falsey, assigns to last value
		}
	}
}
~~~~

~~~~
function vowelCount(str) {
	return str.split("").filter(function(val) {
		return "aeiou".includes(val);
	}).reduce(function(acc,curr){
		return accumulator[current] = (accumulator[current] || 0) + 1; 
		// finds first truthy thing // otherwise if all falsey, assigns to last value
	}, {})
}
~~~~

## Partition 

~~~~
// Idea 1

function partition(arr) {
	// even case
	var evens = arr.filter(function(val){
		return (val % 2 === 0);
	}).reduce(function(acc, curr) {
		return acc.concat(curr);
    }, [])
	// odd case 
	var odds = arr.filter(function(val){
		return (val % 2 === 1);
	}).reduce(function(acc, curr) {
		return acc.concat(curr);
    }, [])	
    return [odds, evens];
}

partition([1, 2, 3, 4, 5, 6]);
~~~~

~~~~
// Idea 2
function partition(arr) {
	return arr.reduce(function(acc, curr, ind, arr) {
        if (curr % 2 === 0) {
            acc[0].push(curr);
            return acc;
        } else if (curr % 2 === 1) {
            acc[1].push(curr);
            return acc;
        }
    }, [[],[]]);
}

partition([1, 2, 3, 4, 5, 6]);
~~~~

************************************

## Questions 

* 

## Ideas & Notes

* Binary search is `O(log n)` but it has to be sorted

* Look up Regular Expressions

* In github, type `t` to look up a specific filename

## To Do

* Double values in an array imperatively, declaratively, and recursively

* Return array with only odd values imperatively, declaratively, and recursively

* Fill in `every` and `findIndex` above

* Figure out how to short circuit stuff with `||`

## Homework Still Pending

* Monday: mergeObjects function

* Tuesday: All bonus functions

* Weds: Everything

* 

## Coming up this week

* Tomorrow: Canvas, vanilla JS / DOM manipulation review

* Fri: ES2015, recap of week

* Outco happy hour this Fri evening

* React.JS 10am-4pm Saturday (kind of advanced for us right now)

* OOP 10am-4pm Sunday (preview of what we'll do next week)

* Next week - make HN Clone, build some games, last week of client-side JS (HTML, CSS, JS)

* 













