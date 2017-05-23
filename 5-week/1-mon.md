# Monday May 22

## Warm Up

* [getAllCombinations](https://repl.it/student/submissions/1023506)
* helper method recursion w/ iteration
* slicing a string

Tim's bitwise operator & binary solution:

`1 << s.length` is 1 with s.length 0's in front of it (in binary!!)

```
function getAllCombinations(s){
  var combos = (1 << s.length) - 1;
  results = [];
  for (var i = 1; i <= combos; i++) {
    var binary = (i).toString(2).padStart(s.length, '0');
    results.push(s.split('').filter((c, j) => binary[j] !== '0').join(""));
  }
  
  return results;
}
```

* `~~` is Math.floor shortcut
* `1234..toString(2)` gives 1234 in binary
* `1234..toString(16)` gives 1234 in hex

## MVC

* model-view-controller
* some frameworks enforce this strictly; Rails has folders for each of these
* database talks to model, model talks to controller, controller talks to view
* how does this work? 

### Model

* encapsulates logic around data - associations/relationships (1:1, 1:M, M:M)
* does not talk to the view
* `models.py`

### Controller

* "brains" behind the operation
* request/response
* "fat model, skinny controller"

### View

* `views.py`
* so far they've been in our `templates` folder

## Blueprints with Flask

* every resource is encapsulated in its own blueprint
* separate file for each resource
* even with nested routes, they will still be separate blueprints
* when we say `from project` it will refer to the `__init__.py` file *inside* of `project`
* [Blueprints with Flask](https://github.com/rithmschool/python_curriculum/blob/master/Unit-02/01-blueprints.md)

************************************

## Questions 

* 

## Ideas & Notes

* Bitwise operators - look into to shorten code (lower-level langs like C)
* Binary 
* Bitshifting

## To Do

* 

## Coming up this week

* 

