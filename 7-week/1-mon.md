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
		* 


************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

