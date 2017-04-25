# Monday April 24 

## Warm Up

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

* Suppose we have two functions, ```f(n)``` and ```g(n)```. We say that ```f(n) = O(g(n))``` (read ```'f of n is big O of g of n'```) if there exists some positive constant ```C``` such that ```f``` is eventually less than ```C * g```. 

* When f and g are both functions of the same variable, we sometimes omit the variable entirely, and write ```f = O(g)```.

* Other times, we may write the explicit formula for g, if we have one. For example, if g is the function ```g(n) = log n```, we might see an expression like ```f = O(log n)```.

## More Big O Details

~~~~
O(n!) > O(2^n) > O(n^2) > O(n log n) > O(n) > O(log n) > O(1)
~~~~

* If you have a constant function (i.e. ```a + b```) it doesn't matter how big a and b are because calulation time is negligible, because languages set upper limits for how large your integers can be -- ex. for Javascript it's approx. 1.7e308 

* **Cool Thing** Can try timing before & after running a function, then plotting the results, to guesstimate the runtime! 

* Binary Search - if array already sorted, you can find value fast

  * start at middle, check if value less than or greater than

  * chop array in half and go to middle of this half

  * keep doing this until you get the value

  * this algorithm is ```O(log n)```

## Time Complexity vs. Space Complexity

* How much **new** space did the function use (i.e. do NOT include the size of the input in calculating this)

 * "auxiliary" space complexity

## Testing with Mocha & Chai! 

* Red / Green / Refactor --> write tests that fail first, then write minimal code and fix until they're all green, then refactor if you want to make the code more efficient

* ```deep.equal``` works with objects as well as arrays; it's about equivalent values whereas ```===``` is about locations in memory

~~~~
describe("Function I'm testing", function() {
	it("thing testing", function() {
		expect(func(argum)).to.equal(bool);
	});
});
~~~~

## Exercises

* fork & clone repo, push to my remote, make a pull req

************************************

## Questions 

* Look up immperative vs. declarative

* Math symbols in Sublime Text / inside a Markdown file (looks like both HTML and LaTeX have ways to do this)

* What does that upper limit integer in JS look like down to the bit or byte level of the computer's machinery? 

* Look up JS map function

* Black-box testing vs. white-box testing

* Ask Matt if he's heard of Burn Math Classå

* Ask for recommendations on books about Big O and intuition building around logarithmic (log n) / linear (n) / quadratic (n^2), cubic (n^3), or polynomial (n^k) / exponential (2^n) -- can be mathematically rather than in the context of programming / computer science 

## Ideas & Notes

* Earth is the densest planet! Cool! (*in the solar system)

* If you're using zsh you don't need to write ```cd```, but can just type the folder name

* Cmd + / to comment out an entire line in sublime

* NaN !== NaN -- only type that isn't equivalent to itself

* If a function mutates the argument that is passed in it's called "not pure"

## To Do

* **Do one of the tutorials to build 2048!**

* Do some tutorials about Sketch to get better at UI Design!

* **Keep doing Khan Academy**

* Buy Art of Problem Solving books **after** Khan Academy is done

* **Do Data Structures & Algorithms workbook evenings & weekends**

* **Try out CodeWars - stop being scared of it >:(**

* **Try out HackerRank - stop being scared of it >:(**

* [CS Fundamentals > Big O exercises](https://www.rithmschool.com/courses/javascript-computer-science-fundamentals/introduction-to-big-o-notation)

* [Adv JS > Intro Testing w/ Mocha & Chai exercises](https://www.rithmschool.com/courses/advanced-javascript/introduction-to-testing-with-mocha-and-chai)

* Write our own Kata on Codewars because you have to make a lot of tests

* Try to write pseudocode & implement the sub-O(n^2) algorithm for stock price problem

 * [stack q](http://stackoverflow.com/questions/7086464/maximum-single-sell-profit)

 * [another stack q](http://stackoverflow.com/questions/9514191/maximizing-profit-for-given-stock-quotes)

 * [careercup q](https://careercup.com/question?id=9663203)

 * [geek something](http://www.geeksforgeeks.org/stock-buy-sell/)

* functional programming!!! remember that!!!

* Project Euler problems

## Rithm topics for next few weeks

* CS Big O & Recursion

* remaining this week + next week - Advanced JS

* then later - Python 

* after that - stuff that's not in the course materials

* sorting algorithms and such will be later in the course






