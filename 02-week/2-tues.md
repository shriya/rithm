# Tuesday May 2

## Warm Up
* [Repl.it Truncate](https://repl.it/student/submissions/905109)
* How to know an algorithm is probably `O(log n)`? If it's dividing and conquering; if you work on half the input or 1/3 of the input at each iteration (rather than all of it) 

## AJAX
* Make sure not to try an execute code block before data is recieved 

```
$(function() {

	var pokemonData;

	// res is "response"
	// make request to get from this URL
	// when we get a response back, console.log it 
	// asynchronous; by default timers and other asynchronous requests 
		// run asynchronously - doesn't "stop" the program
	$.get('http://pokeapi.co/api/v2/pokemon/', function(res) {
		pokemonData = res;
		console.log("response recieved", pokemonData);
	})

});
```

* You can NOT put `console.log("response recieved", pokemonData);` outside of that function assuming it will be updated after; the get request is put on the call stack to be run asynchronously

```
// app.js

$(function() {

  var pokemon = [];
  var $pokemon = $("#pokemon");

  $.get('http://pokeapi.co/api/v2/pokemon')
  .then(function(res) {
    pokemon = pokemon.concat(res.results);
    return $.get(res.next);
  })
  .then(function(res) {
    pokemon = pokemon.concat(res.results);
    return $.get(res.next);
  })
  .then(function(res) {
    pokemon = pokemon.concat(res.results);
    return $.get(res.next);
  })
  .then(function(res) {
    pokemon = pokemon.concat(res.results);
    return $.get(res.next);
  })
  .then(function(res) {
    pokemon = pokemon.concat(res.results);
    var randomIndex = Math.floor(Math.random() * pokemon.length);
    var randomPokemon = pokemon[randomIndex];
    return $.get(randomPokemon.url);
  })
  .then(function(res) {
    var $h2 = $("<h2>", {
      text: res.name
    });
    var $img = $("<img>", {
      src: res.sprites.front_default,
    });
    var $ul = $("<ul>", {text: "Types:"});
    res.types.forEach(function(currentType) {
      $ul.append($("<li>", {text: currentType.type.name}));
    });
    $pokemon.append($h2, $img, $ul);
  });

});
```

```
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sweet AJAX App!</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
</head>
<body>
  <h1>Here are some Pokemon!</h1>
  <div id="pokemon">
    
  </div>
  <script
    src="https://code.jquery.com/jquery-3.1.1.js"
    integrity="sha256-16cdPddA6VdVInumRGo6IbivbERE8p7CQR3HzTBuELA="
    crossorigin="anonymous"></script>
  <script src="app.js"></script>
</body>
</html>
```

* example with promises: 

```
var p = new Promise(function(resolve, reject) {

    setTimeout(function() {
    
        if (Math.random() < 0.5) {
            resolve("success!")
        } else {
            reject("failure 1 :(")
        }
    
    }, 1000)

})

p
.then(function(data) { 

  return new Promise(function(resolve, reject){
    setTimeout(function() {
    
        if (Math.random() < 0.5) {
            resolve("success again!")
        } else {
            reject("failure 2 :(")
        }
    
    }, 1000)
  })

})
.then(function(data) { console.log(data); })
.catch(function(data) { console.log(data); })
```

## Hack or Snooze with AJAX

* to look at working app, clone the solutions repo to see demo of how it's supposed to work
* when page loads, make request to get stories; links work
* can't fave anything until logged in 
* if i want to log in, can do that - then you get to see all your own favorites (stars appear upon login)


```
$.ajax({
	method: "POST",
	url: "url-here",
	header: {
		Authorization: "something"
	}, 
	contentType: "application/JSON",
	dataType: "JSON",
	data: {
		email: "email",
		password: "password"
	}
})
```

```
data: JSON.stringify() {

}
```

## Intermediate JS Part 2

### Intro to jQuery

* `$` is the `jQuery` function; so `($ === jQuery) should be `true` as long as we've included `jQuery` on our page
* `<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>`
* `$` usually takes just one argument; a CSS selector or JS reference

```
$("div") === jQuery("div") 

===

div {
	// css goes here
}

```

* `$("div")` does roughly the same thing as `document.getElementsByTagName("div")`
* 

### Intermediate jQuery



### How the Web Works

### AJAX with jQuery

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 





