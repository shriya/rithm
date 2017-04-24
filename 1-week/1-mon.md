# Monday April 24 

## Warm-Up

~~~~
function addUpTo(num) {
	var sum = 0;
	for (var i = num; i > 0; i--) {
		sum += i;
	}
	return sum;
}
~~~~

* pro: easy to understand what it's doing

* con: takes up more time & space, does ```num``` operations

~~~~
function addUpTo(num) {
	return num * (num + 1) / 2;
}
~~~~

* pro: takes up less time & space (3 operations)

* con: hard to understand what it's doing when reading

## Lead in to Big O

~~~~
var t1 = Date.now();
addUpTo(100000000);
var t2 = Date.now();

console.log("Time Elapsed:", t2-t1);

>> Time Elapsed: 152
~~~~

* Different computers have different speeds, and it depends on what else your computer is doing

* So using milliseconds to determine more efficient algorithm doesn't make sense



## Big-O; space complexity vs. time complexity



## Questions 

* Look up immperative vs. declarative






