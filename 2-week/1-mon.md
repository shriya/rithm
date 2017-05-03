# Monday May 1

## Warm Up

* Repl.it [Collatz Sequence](https://repl.it/student/submissions/895532)
* [Ternary operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

## Intermediate JS Part 2

* Build project today & tomorrow
* Project will use JQuery & AJAX

### jQuery

* originally trying to solve browser compatibility issues
* valuable to switch between vanilla JS and jQuery (but anything you can do in jQuery can be done in Javascript)
* to use jQuery in the chrome console, you need to be on a page that loads [jQuery](http://jquery.com/) 
* you can check this by typing `jQuery` or `$` in the chrome console and seeing if the jQuery function pops up

### DOM Query Methods

* in Javascript
	* `var blocks = document.querySelectorAll("h2.block")`
	* `blocks.innerText = "hello";`
	* (have to loop over all)

* in jQuery
	* `var $blocks = $("h2.block");`
	* `$blocks.text("hello!");`
	* don't have to write a loop; jQuery will iterate for you

```
$blocks
	.text("new text")
	.css("background-color", "green")
```

* Event listeners

```
$blocks.on('click', function(e) {
	console.log(`YOU CLICKED ON ${e.target}`);
});

// event target is not a jQuery object! 
// need to wrap it in the jQuery function: 
// $(e.target) 
```

### To Do jQuery App

* Command + Shift + P (in Sublime) to get search
* form submissions in JS: **need** to make sure you don't refresh on submit: `e.preventDefault();`
* 



