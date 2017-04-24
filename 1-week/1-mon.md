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

* Use space complexity instead 

## Big O Notation

~~~~
f = O(g)
~~~~

Working definition of a function being "less than" another: 

````f < g if f(x) < g(x)```` <html>&forall;</html> ```x```

* Suppose you have two functions, f and g. It's often the case that f is not eventually less than g, but f *is* eventually less than some constant multiple of g. Let's take a look at some examples of this phenomenon.

### Definition of Big O!

* Suppose we have two functions, f(n) and g(n). We say that f(n) = O(g(n)) (read 'f of n is big O of g of n') if there exists some positive constant C such that f is eventually less than C * g. 

* When f and g are both functions of the same variable, we sometimes omit the variable entirely, and write f = O(g).

* Other times, we may write the explicit formula for g, if we have one. For example, if g is the function g(n) = log n, we might see an expression like f = O(log n).

~~~~
O(n!) > O(2^n) > O(n^2) > O(n log n) > O(n) > O(log n) > O(1)
~~~~





















## Questions 

* Look up immperative vs. declarative

* Math symbols in Sublime Text / inside a Markdown file (looks like both HTML and LaTeX have ways to do this)

* 

## Ideas

* Ask Matt if he's heard of Burn Math Class

* Ask for recommendations on books about Big O and intuition building around logarithmic / linear / quadratic / exponential 

## Future

* CS Big O & Recursion

* remaining this week + next week - Advanced JS

* then later - Python 

* after that - stuff that's not in the course materials






