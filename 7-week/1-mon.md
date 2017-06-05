# Monday June 5

## Warm Up

* [findTriples](https://repl.it/student/submissions/1080530)

```
function findTriplets(arr){

  // I still don't know how to approach permutation and combination problems -_- Need lots of practice

  var count = 0;
  for (var i = 0; i < arr.length; i++) {
  	for (var j = 1; j < arr.length; j++) {
  		for (var k = 2; k < arr.length; k++) {
  		  if ((i !== j) && (j !== k) && (i < j) && (j < k)) {
    		  if (arr[i] + arr[j] + arr[k] === 0) {
    				count ++;
    			}
  		  } 
  		}
  	}
  }
  
  return count;
}
```

## Node.js

* our runtime is asynchronous 
* listening for events, events are HTTP requests (routes)
* then execute callback function
* node is great for lots of I/O (input/output)
* works well with websockets (real-time interactivity)
* python has GIL - global interpreter lock
* javascript is single-threaded
* JS event loop - stack, queue, heap
* for loops are synchronous; they'll BLOCK the code from running!!
* node is great for [serialization](https://en.wikipedia.org/wiki/Serialization) - better than flask 'jsonify'
* good for building APIs quickly
* callback pattern in node; second parameter of request functions is a callback function, first argument of THOSE functions is an error

```
var request = require("request");

app.get('/', function(req,responseFromExpress){
  request.get('https://github.com/api/users/elie').then(function(responseFromRequest,body){
    var user = db.User.findOne({name: body.name}).then(function(data){
      responseFromExpress.render('index.html', {user})  
    })
  }).catch(function(err){
    throw err;
  })
})
```

* REQUEST/RESPONSE in HTTP happens and then closes
* Web Sockets (socket.io!!) let you build near-real time (webRTC is true real time) technology -- ex. chat room; lots of Input & Output -- ex. video chat
* server-side templating with node - 
	* EJS - embedded JS (not common)
	* Pug (formerly Jade) - one of the most popular! 
		* don't need closing tags
		* indentation-based
	* Handlebars - variation of client-side templating

## MongoDB

* In Postgres & SQL, we have Databases which contain Tables with Rows & Columns, and Relationships/Associations between Tables
	* the structure of all of our tables & our data in a relational database is called our Schema
* **NoSQL** is a term for databases that don't use SQL 
	* **key-value databases** (fast lookup!) - [redis](https://redis.io/) - temporary quick-lookup storage; ex. 10 email invites to be sent, [cassandra](http://cassandra.apache.org/) - caching done w/ key-value storage
	* **graph databases** - data structure: vertices connected w/ edges - [neo4j](https://neo4j.com/)
	* **document databases** - [MongoDB](https://www.mongodb.com/) - contain collections (rather than tables) -- buckets with no relationships between them (not relational database) -- collections contain documents (documents are like objects -- keys + values -- both have to be strings but no structure of what the documents have to look like) - stored in a binary representation called BSON. the way we organize our collections is Schemaless. no concept of migrations, since everything is subject to change!! 
		* use cases: MEAN stack (Mongo, Express, Angular, Node), use JS to query the db. 
		* ORMs with Node - Waterline, Bookshelf, and Sequelize
		* easier to get up & running quickly than Postgres & SQL & SQLAlchemy
		* in a large application you will use multiple databases
* ODM - MongoDB Object Document Manager - If you use [Mongoose](http://mongoosejs.com/docs/guide.html), you need a Scema! whaaat?!
* after making the Schema, export a model
* `global` object is like `window` - but we don't have `window` in node; everything is attached to `global`
* other object we have with node is `process`
* `process.env` returns an object with a bunch of environment variables

## Sharing Code w/ Imports & Exports

* use modules (import/export) to share code between files because we don't have `<script> tags` because we don't have HTML 
* you can overwrite module.exports when you're exporting one single thing; but if you are exporting 2 functions - you put the whole thing into an object   
* define all as `exports.functionName` to make them externally visible via requiring that file

```
// helper.js

exports.add = function(a,b){
  return a+b;
}
exports.subtract = function(a,b){
  return a-b;
}
exports.multiply = function(a,b){
  return a*b;
}
exports.divide = function(a,b){
  return a/b;
}

// 1 - overwrite
// module.exports = add
// 2 - set as object
// module.exports = {
//   add,
//   subtract,
//   multiply,
//   divide
// }
```

```
// main.js

var helperFunctions = require('./helper')

console.log(helperFunctions)
```

## Express Apps

* CRUD on a resource w/ an array as storage
* Yarn is a more modern package manager for node modules; similar to npm
* venv - virtual env - folder with dependencies; virtual environments in flask were an abstraction - so now we have a huge modules folder
* but I don't want to put my node modules on github!! 
* the node version of 'ipython' -- `eval(require("locus"))`
* node version of `debug = True` is `nodemon`
* `res.locals` are variables that can be used in our templates
* `res.locals.name = "shriya"` makes `res.locals` into `{name: "shriya"}`

## Middleware

* request comes in, middleware modifies that request, then response is sent back
* create new error - app.use at the bottom of the file in case none of the other routes were found
* any time you do `app.use` you're using additional middleware
* if you want to write your own middleware, you have to tell node what to do `next` 
* middleware is like a decorator!!! before you run each function, run this other thing first
* if you pass a string into next(), the FIRST parameter of the next function of middleware will contain the value that came from that next; this is how the error handling works!
* if you don't pass in a first param, it doesn't get propogated to the next piece of middleware -- can't just have req,res,next!! 




************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

