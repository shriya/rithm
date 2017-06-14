# Tuesday June 13

## Warm Up

* [InsertionSort & SelectionSort](https://repl.it/student/submissions/1120354)

## React Router

* History API has methods on it like `back` and `forward` 
* [Manipulating the browser history](https://developer.mozilla.org/en-US/docs/Web/API/History_API)
* `pushState` method allows us to update the path in the URL bar and set a state on the history
* you have to install react router! it's not included
* `npm install --save react-router-dom`

```
<Router> 
	<App />
</Router>
```

* Use react-router `Link` instead of an `<a>` tag so that you're not redirected
* `Redirect` is a React component, use like `<Redirect to={something} />`

#### Object desctructuring

```
var person = {name: "Matt", dog: "Whiskey"}
var { name, dog } = person;

```

#### [Auth Example](https://reacttraining.com/react-router/web/example/auth-workflow)

* in the `PrivateRoute`, the `props` inside render are the props of the children (match, location, and history)
* another way to force a redirect; `history.push('/')` -- push new route onto the history object
* `withRouter` is a higher-order component in React (a component that accepts a component inside of it) - gives component inside of it Router props (match, location, and history)

********************
_notes on my own after lecture_

## [History API on MDN](https://developer.mozilla.org/en-US/docs/Web/API/History_API)

* the DOM `window` object has a `history` object that allows you to access the browser history
* to go back a page, `window.history.back();`
* to go forward a page, `window.history.forward();`
* to go to a specific point, the current page is index 0 and to go back x, write -x, or forward x, write x -- `window.history.go(x)`
* to find how many pages are in the history stack, look at its length property -- `window.history.length`
* `history.pushState()` allows you to add history entries
* `pushState()` takes 3 parameters - state object, title, and URL.
	* title isn't used
	* URL is the new history entry's URL - but it won't be loaded by the browser just because pushState() was called.
	* the state object is a javascript object associated with this new history entry. when a user navigates to this state, a `popstate` event is fired, and the `state` property of the event contains a copy of this `state object`. 
* `history` also has `state` 

## Single-Page Applications

* Any client-side (Javascript) applications which have pages & transitions that happen without refreshing the page (or rendering a new HTML file from the server) are called **single page applications**
* To the user, it should still feel like a server-based web app - which means the back button should work, and bookmarking a specific page should still work
* for an imaginary site `example.com`:

```
// We can store some data we care about here
var state = { data: "value" };

// browser url will change to https://www.example.com/yoyo.html
window.history.pushState(state, "title not used right now", "yoyo.html");
```

* we're going to abstract this away by using `react-router`

## [React Router](https://github.com/rithmschool/react_curriculum/blob/master/Unit-02/01-react_router.md)

* The `Route` React component (which you need to `npm install` and then `import` to use) tells the router which route triggers which component loading on the page! First few props we are using are `path` which gives the string path (ex. `'/'`), and `component` which is a component like `{About}`
* We use the `Link` React component instead of `<a>` tags for routes; they have the prop `to` which we use like this: `<li><Link to="/about">About</Link></li>`
* Whenever you click on a `Link` component, react uses `window.history` to change the url in the address bar. The `Route` component renders the component specified in the `component` attribute whenever the current url path matches the path attribute. 




************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 