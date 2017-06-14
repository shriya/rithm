# Thursday May 4

## Warm Up

* [Object-Oriented Bank w/ Accounts](https://repl.it/student/submissions/921092)
* Put the functions on the class's prototype and define them outside of the class definition; achieves same thing as setting properties 
* Saves memory because you don't create and define a new function each time an instance of the class is created with `new`

## More Object Oriented Programming

`"Prefer composition over inheritance"`

### Composition
* Building up components, then using those components in other classes
* Uses instances of class inside another class (rather than having classes inherit behavior from parents)

### Encapsulation
* not allowing access or knowledge of internal structures of an implementation
* combining data and functions into a class so that data is accessed through the functions rather than being public 
* public data vs. private data
* creating functions that make it easier for the user to understand a class' interface and abilities (so they don't have to understand the internal construction of the class and access + modify values manually)
* ex. `bank.withdraw(id, 100)` rather than `bank.accounts[id].balance -= 100`

### Abstraction
* separating interface from implementation 
* showing only relevant data and hiding details of an object from the user 
* think: Does it make sense for this object to do this "action"? (function)

### Inheritance
* Child classes inheriting functionality from their parent class
* when an object is based on another object 

### Polymorphism
* Different objects can have the same method on them but under the hood it's implemented differently 
* Ex. Square, Circle, and Triangle inherit from class Shape - all have a Draw function, but it's implemented differently on each one - but you just need to call shape.Draw() without knowing how they all work under the hood

## Walking through flash card app example

* Model-View-Controller (MVC) Architectural pattern: 

* `Deck` (controller / modifier)
	* list of all cards (instances of Card)
	* advances to next card
	* shuffle function
* `Card` (model / data)
	* front data
	* back data
* `Card View` (view)
	* which card is up
	* contains one Card

* Made separate JS files for each of the classes, and put them all before `main.js` in the `index.html` (so it can see them)
* In an event listener, `this` is set to e.target, so to call a function that's part of a class, you have to bind the function that is already in that class -- ex. `this.flip.bind(this)`


## Tic Tac Toe

* Board is a 3x3 grid, user switches back and forth X to O, if a row or column is filled with all of one type (X or O), that player wins. If it's filled but no rows, it's a Tie. 
* Keep track - maximum 9 turns
* Need a button to clear the board & restart
* Each time someone clicks in a square, the relevant X or O appears (squares need 3 states: blank, X, and O) -- need to know which turn/user they're on

#### Classes

* class Board containing 9 instances of class Square
	* new game function - resets the game: clears all squares (makes all instances of Square blank), resets # flipped to zero, resets winner to nobody, etc.
* Squares are updated/modified by class SquareView 
	* three hard-coded properties in the object: blank, X, or O
* SquareView has function that turns blank to X or O depending on game state -- can take in variable that tells the state of the game (whose turn you're on)
* Board needs to track game state: 
	* current turn (pass to squareview function)
	* if there's a row or column --> declare winner and end game
	* number of cards flipped (once you have 9, game has to end --> say win or tie)

#### [OOP Notes](https://github.com/rithmschool/intermediate_javascript/blob/master/unit-01/10-intermediate-oop.md)

************************************

## Questions 

* 

## Ideas & Notes

* put an underscore at the start of variables to denote that they're private, i.e. `var _private = "data"`
* comma-separated variable declarations are all vars: 

```
var first = 1,
	 second,
	 third;
```

## To Do

* 

## Coming up this week

* 

