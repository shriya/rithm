# Wednesday June 7

## Warm Up

* [mergeSortedArrays](https://repl.it/student/submissions/1094074)

## Node & Express JSON APIs

* APIs are fundamentally different than what we've been doing because now instead of refreshing the page with a render or redirect, we're sending responses that don't involve either of those things.
* we need to do client-side templating because we can't do server-side templating
* we're using JSX - XML-like syntax for creating templates (in React)
* server-side router -- listens for HTTP requests and does something accordingly; this is why we wanted to change the URL with [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API)
* only thing we respond with from the server is JSON - with `send`
* mongo stores BSON (binary JSON)
* JSON APIs - building server-side applications that respond with JSON --> renders and redirects are gone
* default action of a form is to refresh the page, make a request, get a response -- we need to prevent the default 
* will use AJAX for all data sent to & recieved from the server 

## Express App with JSON API

* (following along with [app from lecture)](https://github.com/elie/ajax-crud)
* [refactor of yesterday's app with async stuff](https://github.com/elie/mongoose-crud/blob/async-functions/app.js)

## Object Destructuring

```
var obj = {
    name: "Elie",
    moreData: {
        evenMoreData: {
            homeTown: "NJ",
            wiseMan: "Tobi",
            hasBeans: false
        }
    }
}

//

var {homeTown:a, wiseMan:b, hasBeans:c} = obj.moreData.evenMoreData
```

## React!!!!!!

* [Intro to React!!!](https://www.rithmschool.com/courses/react-fundamentals/introduction-to-react)

```
div(attributes, children)

React.createElement(type/component, props, children)

// think of attributes as same as props
// and children as same as children
// type/component is name of component like SuperSweetComponent
```

* each `return` statement has to have one root element -- doesn't have to be a div but it can't be two things


************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 