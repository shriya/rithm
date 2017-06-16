# Thursday June 15

## Warm Up

* Instead, Outco practice problem 4pm-5pm
* frequency hash (object)
* finding intersection of frequency hashes

## React + Redux App Example

* makeup app - clicking on brand name fires a GET request for all product with a brand
* can add to shopping cart, see things in cart, and remove from cart
* state that is shared between the routes (`/brand`, `/brand/:brand`, `/cart`) - what you're going to buy 
* boilerplate for react router: in index.js, wrap `<App />` with `<Route>`
* render `/brands` and `/cart` as routes; make sure `/` redirects to `/brands`
* components are cart & brandPage - stateless functional components that we aren't using outside of MainContent component 
* the `render` prop on `<Route>` should be used on a stateless functional component rather than `component` prop because otherwise it will unmount & remount each component (and refresh the pg)
* reducers: get props `state` and `action` 

```
const rootReducer = (state = DEFAULT_STATE, action) => {
	switch (action.type) 
}
```

* `mapStateToProps` and `mapDispatchToProps`

## Today's Class: Flask + React App

* [Github Repo for this app](https://github.com/rithmschool/react_curriculum/tree/master/Unit-02/examples/redux-auth-client-server)
* Right now we're using webpack for the server with our React apps
* We want an actual backend (that's not local)
* And we want routing to be on the frontend instead of backend
* React frontend makes a GET request w/ AJAX to the Flask backend; Flask returns JSON to the frontend
* we're getting the same HTML/CSS/JS back no matter what URL is in the bar; then React loads once it reads the index.js file and hits the ReactDom.render line - THEN React takes over 

#### What happens when the page loads?

* first looks at HTML file (for our react apps - in the public folder, it's `index.html` - has a div with a root id which is the second argument to `ReactDOM.render` in `index.js`) parsed as text - makes another `GET` request for each thing included via a link or script tag
* then looks at `bundle.js` file when it's included in the html file
* this contains a reducer (with the Babel compilation down to ES5) and loads everything into the window - then where `ReactDOM.render` is called (in `index.js`), the component exists **POOF!**
* now since we have flask, if we look at the `__init__.py` there are blueprints for two resources - users and puppies

#### Our setup

* The two apps are totally separate apps; the only way they communicate is because React is running (in this case) on localhost:3000 and the Flask app is making GET/POST requests to localhost:3000
* For creating a new ToDo, React makes an AJAX POST request to the Flask backend - the header includes a JSON string with the actual data of the todo text.
* In Flask app, goes into SQLAlchemy and creates a new ToDo based on the JSON, it's committed to the Postgres database, then a response is sent back - an HTTP Status Code (201) plus header & data to the React frontend. The "data" will include the `id` that Postgres gave that ToDo item in the database
* The persistence is now on the backend in our CRUD apps; our usual routes (/todo, /todo/4) are on the frontend - the flask app has routes to the API instead

#### Authentication

* We added a token in Local Storage at the particular IP address and then could log in w/ Tim's account
* So obviously this is not that robust auth

## Reviewing Old React Stuff So I'm Less Confused

#### JSX

* [JSX in Depth](https://facebook.github.io/react/docs/jsx-in-depth.html)
* Capitalized types indicate that the JSX tag is referring to a React component.
* These tags get compiled into a direct reference to the named variable, so if you use the JSX `<Foo />` expression, `Foo` must be in scope.

```
// using Dot Notation to access components

import React from 'react';

const MyComponents = {
  DatePicker: function DatePicker(props) {
    return <div>Imagine a {props.color} datepicker here.</div>;
  }
}

function BlueDatePicker() {
  return <MyComponents.DatePicker color="blue" />;
}
```

* Javascript expressions can be passed in as props by surrounding them with {}: 

`<MyComponent foo={1 + 2 + 3 + 4} />`

* String literals don't need the {}: 

```
<MyComponent message="hello world" />

// is the same as

<MyComponent message={'hello world'} />
```

* You can use the ... (spread operator) to pass in the whole props object if you already have it: 

```
function App1() {
  return <Greeting firstName="Ben" lastName="Hector" />;
}

// is the same as

function App2() {
  const props = {firstName: 'Ben', lastName: 'Hector'};
  return <Greeting {...props} />;
}
```

* passing in JS expressions as children by wrapping in {}: 

```
function Item(props) {
  return <li>{props.message}</li>;
}

function TodoList() {
  const todos = ['finish doc', 'submit pr', 'nag dan to review'];
  return (
    <ul>
      {todos.map((message) => <Item key={message} message={message} />)}
    </ul>
  );
}
```

* functions as children - props.children works like other props: 

```
// Calls the children callback numTimes to produce a repeated component
function Repeat(props) {
  let items = [];
  for (let i = 0; i < props.numTimes; i++) {
    items.push(props.children(i));
  }
  return <div>{items}</div>;
}

function ListOfTenThings() {
  return (
    <Repeat numTimes={10}>
      {(index) => <div key={index}>This is item {index} in the list</div>}
    </Repeat>
  );
}
```

## Reviewing ES6 Syntax

#### Arrow Functions

* [MDN Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

```
// Parenthesize the body of function to return an object literal expression:
params => ({foo: bar})

// Rest parameters and default parameters are supported
(param1, param2, ...rest) => { statements }
(param1 = defaultValue1, param2, …, paramN = defaultValueN) => { statements }

// Destructuring within the parameter list is also supported
let f = ([a, b] = [1, 2], {x: c} = {x: a + b}) => a + b + c;
f();  
// 6
```

#### Rest Parameters

* [Rest parameters on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
* Rest parameters can be destructured

```
function f(...[a, b, c]) {
  return a + b + c;
}

f(1)          // NaN (b and c are undefined)
f(1, 2, 3)    // 6
f(1, 2, 3, 4) // 6 (the fourth parameter is not destructured)
```

#### Destructuring Assignment

* [MDN Destructuring Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```
var a, b, rest;
[a, b] = [10, 20];
console.log(a); // 10
console.log(b); // 20

[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(a); // 10
console.log(b); // 20
console.log(rest); // [30, 40, 50]

({a, b} = {a: 10, b: 20});
console.log(a); // 10
console.log(b); // 20
```

## Making Simpler Apps to Catch Up

#### Tic Tac Toe

* [Tic Tac Toe Tutorial](https://facebook.github.io/react/tutorial/tutorial.html) - finishing tutorial
* when rendering a list of items (with `<li>`s), react stores info about each item in the list. when updating the list, React needs to determine what has changed -- React has to have a `key` property on each element in the list 
* **it cannot be referenced with `this.props.key`; it's something React uses automatically when deciding which children to update -- Reach maintains the state of items that were not modified and only updates the one(s) with matching key(s)**
* they don't have to be globally unique, just unique relative to immediate siblings

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 