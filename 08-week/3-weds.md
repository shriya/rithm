# Wednesday June 14

## Warm Up

* [Merge Sort](https://repl.it/student/submissions/1125319)

## [React Router Continued](https://github.com/rithmschool/react_curriculum/blob/master/Unit-02/01-react_router.md)

* [Destructuring example](http://wesbos.com/destructuring-objects/)
* [Destructuring in more depth; for...of, reassigning names, etc.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

### More History API

* If you are updating the URL, it still has to have the same origin as the current one, otherwise you could risk a security flaw where you could easily trick users into thinking they were on a completely different website; i.e. if we were at rithmschool.com and did: `history.pushState(null, null, 'https://twitter.com/hello');`, we would get an error. We can do `history.pushState(null, null, 'hello');`, but cannot change the rest of the URL
* If a change had a # in front (like when you click an anchor tag with an href of "#target" or "#") it doesn't reload the page

### withRouter 

* You can get access to the router object’s properties via the withRouter higher-order component. 
* This is the recommended way to access the router object. 
* withRouter will re-render the component every time the route changes.

example: 

```
const AuthButton = withRouter( props => (
  fakeAuth.isAuthenticated ? (
    <p>
      Welcome! 
      <button onClick={() => {
        fakeAuth.signout(() => props.history.push('/'))
      }}>Sign out</button>
    </p>
  ) : (
    <p>You are not logged in.</p>
  )
))
```

### Redirect

* Rendering a `<Redirect>` will navigate to a new location, overriding the current location in the history stack. 
* props on this component include `to`, whose value is the path/URL or object to redirect to

```
<Redirect to={{
	pathname: '/login',
	state: { from: props.location }
}}/>
```

### Link

* Provides declarative, accessible navigation around your application
* Pathnames or objects to link to using this `<Link>` component

## [Intro to Redux](https://github.com/rithmschool/react_curriculum/blob/master/Unit-02/02-redux_intro.md)

* [Tutorial w/ Illustrations on CSS Tricks](https://css-tricks.com/learning-react-redux/)
* [Cartoon intro to Redux](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6)
* more tomorrow

## Reviewing Old React Stuff So I'm Less Confused

### React Components & Props Review

* Components must return a single root element. This is why we add a `<div>` to to wrap around other elements.
* Props are read-only; the component has to be a pure function and not change its own inputs. It must always return the same result for the same inputs.
* **All React components must act like pure functions with respect to their props.**
* "Functional Stateless Components" -- components that have no state and return the same markup given the same props, written as functions
* "This pattern is designed to encourage the creation of these simple components that should comprise large portions of your apps."

### Rest & Spread Operators - ES6

* Rest & Spread for objects are useful to get remaining keys & values in React: 

```
// REST
let { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }

// SPREAD
let n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }
```

* You can use the [rest/spread operators on objects](https://github.com/tc39/proposal-object-rest-spread)

```
{routes.map((route, i) => (
  <RouteWithSubRoutes key={i} {...route}/>
  
  // above is the same as 
  
  <RouteWithSubRoutes key={i} path={route.path} component={route.component}/>
))}

// we need a key any time we have an array of values so that React can iterate through that array
```

```
let aClone = { ...a };

// is the same as: 

let aClone = Object.assign({}, a);
```

## Reviewing JS Iterators

#### `forEach` 
* first parameter is a callback, with up to 3 parameters: value at current index, current index, and array itself
* always returns `undefined`

```
var arr = [1,2,3,4];
arr.forEach(function(val,idx,arr){ 
	console.log(val);
	console.log(idx);
});
```

#### `map`

* structure is same as forEach; first parameter is a callback, with up to 3 parameters: value at current index, current index, and array itself
* returns a new array of values returned in the callback.

```
var arr = [1,2,3,4];
arr.map(function(val, index, array){
	return val * 2;
}); // [2,4,6,8]

var tripledValues = arr.map(function(val,index,arr){
    return val*3;
});
```

#### `filter` 

* same structure again; first parameter is a callback, with up to 3 parameters: value at current index, current index, and array itself
* inside the callback, you must `return` an expression that evaluates to `true` or `false` (a boolean); if it "passes" (is true), it's added to the return array. Otherwise, it is not.
* an array of the filtered values is returned from `filter`

```
var arr = [1,2,3,4];
arr.filter(function(val){
	return val > 2;
});
```

#### `reduce` 

* takes something and reduces it to a single value
* can be a string, boolean, object, array, 2D array...
* callback function to reduce takes 4 parameters: 
	* start/previous/accumulator (will be prev value returned by callback)
	* value
	* index
	* array (or object)
* can pass in second parameter AFTER callback, which will be the initial value before iteration has started
* otherwise, it will assume first element of the array is the initial value and start itation from the second

```
var arr = [2,4,6,8];
arr.reduce(function(acc,next){
	return acc + next;
},5);

// returns 25; sum of all elements in array + 5
```

* you can obtain different data types by changing the initial value of the accumulator
* reducing an array to an object: 

```
var arr = [1,2,3,4,5,6];

arr.reduce(function(acc,next) {
	if(next % 2 === 0) {
		acc['key_' + next] = next;
	}
	return acc;
},{});

// returns Object {key_2: 2, key_4: 4, key_6: 6}
```

* you cannot use `break` or `continue` in Iterators, only in `for` loops
* [More about `reduce`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=example)
* [reduceRight](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceRight?v=example)

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 