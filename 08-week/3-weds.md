# Wednesday June 14

## Warm Up

* [Merge Sort](https://repl.it/student/submissions/1125319)

## [React Router Continued](https://github.com/rithmschool/react_curriculum/blob/master/Unit-02/01-react_router.md)

* [Destructuring example](http://wesbos.com/destructuring-objects/)
* [Destructuring in more depth; for...of, reassigning names, etc.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

### More History API

* If you are updating the URL, it still has to have the same origin as the current one, otherwise you could risk a security flaw where you could easily trick users into thinking they were on a completely different website; i.e. if we were at rithmschool.com and did: `history.pushState(null, null, 'https://twitter.com/hello');`, we would get an error. We can do `history.pushState(null, null, 'hello');`, but cannot change the rest of the URL
* If a change had a # in front (like when you click an anchor tag with an href of "#target" or "#") it doesn't reload the page

### React Components & Props Review

* Components must return a single root element. This is why we add a `<div>` to to wrap around other elements.
* Props are read-only; the component has to be a pure function and not change its own inputs. It must always return the same result for the same inputs.
* **All React components must act like pure functions with respect to their props.**
* "Functional Stateless Components" -- components that have no state and return the same markup given the same props, written as functions
* "This pattern is designed to encourage the creation of these simple components that should comprise large portions of your apps."

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

### Rest & Spread Operators - ES6

* Rest & Spread for objects is useful to get remaining keys & values in React: 

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


************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 