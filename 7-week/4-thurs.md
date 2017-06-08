# Thursday June 8

## Warm Up

* [Push, Pop, and Print a stack!](https://repl.it/student/submissions/1100281)

## React

* `create-react-app` gives you a boilerplate for your application
* use this for new React projects 


```
import React, {Component} from 'react';

class Example extends Component {
	render() {
		return (
			<div className="person"> </div> 
		)
	}
}
```

* to use bootstrap, `npm install bootstrap` then in index.js `import './path-to-bootstrap'` -- same with font-awesome
* have to make sure to render children; make sure NOT to have a prop of "children" since this is a keyword
* access currently highlighted component in React chrome console by typing `$r` 

## Class Constructors

```
class Person {
	// NEED to specify constructors!!
	constructor(name) {
		this.name = name;
	}
	
	sayHi() {
		return `Hi I'm ${this.name}`;
	}
}

var shriya = new Person("Shriya");

class Instructor extends Person {
	constructor(myName, employer) {
		super(myName);
		this.employer = employer;
	}
}

var tim = new Instructor("Tim", "Rithm School");

tim
>> Instructor {name: "Tim", employer: "Rithm School"}

Instructor.prototype
>> Person {constructor: function}

Person.prototype
>> Object {constructor: function, sayHi: function}

var name = "matt";

// ES5
var obj = {
    name: name,
    sayHi: function sayHi() {
        return this.name + " says hi";    
    }
}

// ES2015
var obj = {
    name,
    sayHi() {
        return this.name + " says hi";    
    }
}
```










************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 