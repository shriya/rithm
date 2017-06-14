
# Monday May 8

## Warm Up

* [Repl.it findPair()](https://repl.it/student/submissions/942195)
* to get length of set in JS, use .size 
* 2 pointers problems: can start pointers at:
	* beginning & end
	* both in middle
	* adjacent pair at the beginning

## Python  

* Differences Python vs. JS
	* More data types
		* set()
		* dict --> like objects (difference: 
		* list --> like arrays
		* tuple
	* No sources tab :( 
		* pdb (python debugger)
		* iPython

### Dictionaries

```
first_dict = {1: "one", 2: "two"}

my_dict[1]
>> "one"

type(my_dict[1])
>> str

# no dot notation; i.e. my_dict.1 does not work!! 

d = dict(name = 'Elie', job = 'instructor', is_hilarious = True)
# above assigns key and value pairs

d.keys()
>> dict_keys(['is_hilarious', 'job', 'name'])

type(d.keys())
>> dict_keys

for val in d.keys(): 
	print(val)
>> prints all keys on new lines

d.values()
>> dict_values(['Elie', 'instructor', True])

# BUT -- dict_values does not support indexing
# so you can turn it into a list: 

list(d.values())

# now you are allowed to do:
list(d.values())[0]
```

### Primitive Data Types

```
# 3 is an int
# 3.3 is a float
# 'awesome' is a str

### DO NOT reassign primitives; if you say str = 'stuff', now you can't use str

# True and False are both bool 

# dict
# list
# tuple
# set

```

### Lists & List Comprehension

```
l = [1,2,3,4,5]

for val in l:
	print(val)
	
1
2
3
4
5

# no, better way to do this: 

[val for val in [1,2,3,4]]
>> [1,2,3,4]

# these have to be the same name
# 2nd is defined, first is not 

# can be random names

[burrito for burrito in [1,2,3,4]]
>> [1,2,3,4]

[value*2 for value in [1,2,3,4]]
>> [2,4,6,8]

[value for value in [1,2,3,4] if value*2 > 5]
>> [3,4]
```

#### Comparing Data Structures

```
l = [1,2,3]

l2 = [1,2,3]

l == l2
>> True

l is l2
>> False

# you can compare them for equality
# but they still don't point to the same reference 
```

#### Ternary-ish

```
'YEAH' if 1 == 1 else 'NO!'
```

### String Operations

```
'awesome'.count('e')
>> 2

d = {}

for char in 'awesome': 
	pass
	
# pass lets you skip over indentation block so you can do things later (temporary placeholder, or "skip over")
# will not *stop execution of code* -- will still run things after (unlike break)
# will just stop you from getting an error for an unexpected indentation or lack of indented code
```

### Dictionary Comprehension

```
d = {'name':'shriya'}

d.items()
>> dict_items([('name', 'shriya')])
# that's a tuple! 

{value:'awesome'.count(value) for value in 'awesome'}
>>  {'a': 1, 'e': 2, 'm': 1, 'o': 1, 's': 1, 'w': 1}

{value:'awesome'.count(value) for value in 'awesome' if value in 'aeiou'}
>> {'a': 1, 'e': 2, 'o': 1}
```

### Set Comprehension

```
# if you specify one thing, it does set comprehension

{value for value in 'awesome'}
>> {'a', 'e', 'm', 'o', 's', 'w'}

type({value for value in 'awesome'})
>> set
```

### Turn string into list

```
"this is cool".split(" ")
>> ['this', 'is', 'cool']

''.join("this is cool".split(' '))
>> 'thisiscool'
```

### Sorting a list

```
l = [10,4,2,5,1,7]

l.sort()

l 
>> [1, 2, 4, 5, 7, 10]

# but this mutates the list :( 
# so instead:

l = [10,4,2,5,1,7]

sorted(l)
>> [1, 2, 4, 5, 7, 10]

l 
>> [10, 4, 2, 5, 1, 7]
```

### Reverse a string

```
''.join(list(reversed(list('awesome'))))
>> 'emosewa'
# no. no. 

'awesome'[::-1] 
>> 'emosewa'
# this sets to beginning & end -- don't hard-code the values

# lists & strings can be sliced
# [start:end:step]

'awesome'[:1]
>> 'a'

'awesome'[:1:2]
>> 'a'
# ends too soon

'awesome'[::2]
>> 'aeoe'

'awesome'[::10]
>> 'a' 
# can't go beyond the end

'awesome'[-1:]
>> 'e'
# this is all the way at the end; not like "-0"

'awesome'[-2:]
>> 'me'
```

### Scoping with Functions

```
# need to word 'global' to specify that variables are global
# but you shouldn't really use this

>>>> Javascript equivalent: 

function counter() {
	var count = 0;
	return function() {
		count++;
		return count;
	}
}

c = counter();
>> function

c();
>> 1

>>>> Now see it in Python

def counter(): 
	def inner(): 
		inner.count += 1
		return inner.count
	inner.count = 0
	return inner

c = counter()

c()
>> 1

# Decorators: adding additional functionality to functions after 

```

### Generators

```
# function that does not immediately run to completion

# allow us to pause execution of a function and complete it at a later time
# yield keyword inside a function makes it immediately a generator

l = [1,2,3]

def first(l):
	for val in l:
		yield(val)

gen = first([1,2,3])
# a generator object

type(gen) 
>> generator

type(first)
>> function

# useful for asynchronous code
# runs code in function, and pauses execution when it sees "yield"

# __iter__ -- means it can be iterated over
# __next__ -- means next function can be called on it; next 

gen = first([1,2,3])

next(gen) 
>> 1 

next(gen) 
>> 2

next(gen) 
>> 3

next(gen) 
>> (stop iteration error)

for val in gen:
	print(val)
>> 1
>> 2
>> 3

# generators can be iterated over; this just runs it until it's over

l = [1,2,3,4,5]

# want to return 5 if it's in the list

# long way:

for val in l:
	if val == 5:
		print(val)

# good way:

[value for value in l if value == 5]
>> [5]

[value for value in l if value == 5][0]
>> 5

# now try it with generator comprehension
# NOT using the yield keyword if you notice
# next is a function that can be invoked on a generator

next(value for value in l if value == 5)
>> 5

# how do you handle errors?

try: 
	next(val for val in [1,2,3,4] if val == 5]
except StopIteration:
	print('nope!')

# you have to say which error you expect; don't "except" for all possible errors
# if you pass in other (wrong) error, it will error out

# can also chain exceptions:

try: 
	next(val for val in [1,2,3,4] if val == 5]
except KeyError: 
	print('weird')
except StopIteration:
	print('nope!')

# key of types of comprehensions

() # generator comprehension (but also syntax for a tuple)
{} # dictionary or set comprehension (2 values or 1 value)
[] # list comprehension
```

#### Set vs. Tuple

##### Set 
* set is only unique vals {1,2,3}
* can add stuff 
* s = {1,2,3}
* s.add(10)
* great way to get just uniques quickly

##### Tuple
* tuple is not only uniques (1,2,3,3,2,3)
* cannot be changed; have to make new one
* immutable
* fast lookup! 

### Decorators

##### Before a function is run, I want to run something

```
def add(a,b):
	print('hello')
	return a+b

def subtract(a,b):
	print('hello')
	return a-b
```

##### Above is too repetitive; now use a decorator:

```
def print_hello(fn):
	def inner():
		print('hello')
		return fn()
	return inner
	
# ^^ similar to weak closure in JS ^^

def add(a,b):
	return a+b

wrapper = print_hello(add)

wrapper(1,2)
```

##### ^^  THIS DIDN'T WORK!! WHY? ---> 

```

# if you use * you can get all args: 
# like rest and spread in JS
# tuple unpacking --> spread out all of the values in a tuple

def my_fun(*args):
	print(args)
	
my_fun(1,2,3,4)

>> (1,2,3,4)

def my_fun(*args)
	print(*args)

>> 1 2 3 4

# keyword arguments: knowing the name of a parameter and giving it a value
# kwargs

def add(a,b):
	return a+b

add(a=3, b=4)
>> 7

add(b=7, a=2)
>> 9

```

##### BACK to old function

```
def print_hello(fn):
	def inner(*args):
		print('hello')
		return fn(*args)
	return inner
	
# ^^ similar to weak closure in JS ^^

def add(a,b):
	return a+b

wrapper = print_hello(add)

wrapper(1,2)

# print_hello (the function) is a decorator
```

##### this is repetitive (with the wrapper) - how else can we do it? 

```
def more_than_ten(fn):
	def inner(*args):
		if fn(*args) < 10:
			return "The sum is less than ten."
		return fn(*args)
	return inner

@more_than_ten
def must_sum_more_than_ten(a,b):
	return a+b
```

##### should have a doc string to specify what each function does

```
def add_with_doc(a,b):
	"""this function adds two numbers"""
	return a+b

add_with_doc.__doc__
>> "this function adds two numbers"

# if you use with a decorator, function is renamed to inner function's name
# so __doc__ no longer works because the __name__ is the inner name

# so, to preserve: 
# write: 
from functools import wraps

def more_than_ten(fn):
	@wraps(fn)
	def inner(*args):
		if fn(*args) < 10:
			return "The sum is less than ten."
		return fn(*args)
	return inner

# so now the function will have same __doc__ and __name__ as it was before
```

### Modules

```
import 
# keyword that brings in code from somewhere else

# for example:
# gets you just ceil:
from math import ceil

# gets you everything
import math 

# look at everything:
dir(math)

# gets you a few things
from math import ceil,floor

# name of a file (__name__) is __main__ 
# but if imported, name is name of the file (i.e. "helper" for helper.py)

# to make sure import doesn't run the WHOLE file: 

# app.py
from helper import add

# helper.py
def add(a,b):
	return a+b

def secret_method():
	return "DO NOT PRINT ME" 

if __name__ == '__main__':
	print(secret_method())
```


************************************

## Questions 

* 

## Ideas & Notes

* no ternary operators in Python
* Python is generally conducive to more imperative programming rather than declarative
* use `help` and `dir` in iPython
* CTRL + A -- beg
* CTRL + E -- end
* OPTION + L -- option left
* OPTION + R -- option right
* CTRL + W -- delete a word

## To Do

* command line - make multiple files w/ same extension
* `touch {thing1,thing2}.py`
* 

## Coming up this week

* 

