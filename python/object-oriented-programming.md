# Object-Oriented Programming

## Advantages
* create large, modular programs that can easily expand over time
* hide the implementation from the end-user

## Procedural vs. Pbject-Oriented Programming
A procedural program executes line by line as the program is executed. An OOP program focuses on the individual characteristics of each object and what each object can do. A characteristic is referenced by a noun and an action is a verb. For example a sales person object could have characteristics or attributes name, employee Id, pay grade, and actions or methods sell item.

## Object-Oriented Programming (OOP) Vocabulary
* class - a blueprint consisting of methods and attributes

* object - an instance of a class. It can help to think of objects as something in the real world like a yellow pencil, a small dog, a blue shirt, etc. However, as you'll see later in the lesson, objects can be more abstract.

* attribute - a descriptor or characteristic. Examples would be color, length, size, etc. These attributes can take on specific values like blue, 3 inches, large, etc.

* method - an action that a class or object could take

* OOP - a commonly used abbreviation for object-oriented programming

* encapsulation - one of the fundamental ideas behind object-oriented programming is called encapsulation: you can combine functions and data all into a single entity. In object-oriented programming, this single entity is called a class. Encapsulation allows you to hide implementation details much like how the scikit-learn package hides the implementation of machine learning algorithms.


## OOP Syntax
* Capitalize first letter of class name
* Start with `class Shirt`
* Initialize attributes with `__init__`, used to create a specific object of the class
```
def __init__(self, color, size, price):
    self.color = color,
    self.size = size,
    self.price = price
```

* Declare class methods
```
def change_price(self, new_price):
    self.price = new_price

def discount(self, discount):
    return self.price * (1 - discount)
```

* Instantiate an Object
`new_shirt = Shirt('red', 'S', '10')`

* Work with Object
`print(new_shirt.color)`
returns red

NOTE: Accessing attributes directly would be frowned upon in many other languages but not in Python. Instead, the general object-oriented programming convention is to use methods to access attributes or change attribute values. These methods are called set and get methods or setter and getter methods.
```
class Shirt:

    def __init__(self, shirt_color, shirt_size, shirt_style, shirt_price):
        self._price = shirt_price

    def get_price(self):
      return self._price

    def set_price(self, new_price):
      self._price = new_price
```
In the class definition, the underscore in front of price is a somewhat controversial Python convention. In other languages like C++ or Java, price could be explicitly labeled as a private variable. This would prohibit an object from accessing the price attribute directly like shirt_one._price = 15. However, Python does not distinguish between private and public variables like other languages. Therefore, there is some controversy about using the underscore convention as well as get and set methods in Python.

One of the benefits of set and get methods is that, as previously mentioned in the course, you can hide the implementation from your user. Maybe originally a variable was coded as a list and later became a dictionary. With set and get methods, you could easily change how that variable gets accessed. Without set and get methods, you'd have to go to every place in the code that accessed the variable directly and change the code.
Reference: https://www.python-course.eu/python3_properties.php


* What is self?
```
def change_price(self, new_price):
    self.price = new_price
```

`Self` tells Python where to look in the computer's memory for the shirt_one object. And then Python changes the price of the shirt_one object. When you call the `change_price` method, `shirt_one.change_price(12)`, `self` is implicitly passed in.

The word `self` is just a convention. You could actually use any other name as long as you are consistent; however, you should always use `self` rather than some other word or else you might confuse people.


