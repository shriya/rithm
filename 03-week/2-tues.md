# Tuesday May 9

## Warm Up
* [Left-Handed Riemann Sums](https://www.codewars.com/kata/5562ab5d6dca8009f7000050/solutions/python/me/best_practice)
* Tips: 
	* make sure you know what each argument in function is doing
	* check that you're not using any built-in functions as new variables
	* check indentation problems

## OOP in Python; Classes!

* `self` refers to class instance; not as complicated as `this` in JS
* always first parameter to functions

```
class Vehicle: 
	def __init__(self,makemodel,year):
		self.make = make
		self.model = model
		self.year = year
```

```
class Person():
	
	def __init__(self, first_name, last_name):
		self.first_name = first_name
		self.last_name = last_name
		
	def full_name(self):
		return "My name is {} {}".format(self.first_name, self.last_name)
		
#		
		
tim = Person("Tim", "Garcia")
print(tim.full_name())
```

#### Class methods

* Shared functionality on the class
* "cls" here is a reference to the class itself; can be named anything - first arg


```
class Rectangle: 
	
	@classmethod
	def area(cls, w, h):
		return w * h

#

print(Rectangle.area(5,10))
```

#### Inheritance and super class

```
class Vehicle:
    def __init__(self,make,model,year):
        self.make = make
        self.model = model
        self.year = year
    def honk(self):
        return "Beep!"

class Car(Vehicle):
    def __init__(self,make,model,year):
        super().__init__(make,model,year) # this is python3 specific!
        self.wheels = 4
```

## File I/O in Python

* read, write, and append
* csv files

* when using `DictWriter`, use `fieldnames` keyword

```
with open('newfile.csv', 'a') as csvfile:
    data = ['name', 'fav_topic']
    writer = csv.DictWriter(csvfile, fieldnames=data)
    writer.writeheader() # this writes the first row with the column headings
    writer.writerow({
        'name': 'Elie',
        'fav_topic': 'Writing to CSVs!'     
    }) 
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

