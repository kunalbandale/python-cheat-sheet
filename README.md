# 🐍 Python 3 Cheatsheet

## Table of Contents
1. [Variables and Data Types](#variables-and-data-types)
2. [Control Flow](#control-flow)
3. [Functions](#functions)
4. [Collections](#collections)
5. [List Comprehensions](#list-comprehensions)
6. [File Handling](#file-handling)
7. [Modules and Packages](#modules-and-packages)
8. [Error Handling](#error-handling)
9. [Classes and Objects](#classes-and-objects)
10. [Useful Libraries](#useful-libraries)
11. [Decorators](#decorators)
12. [Generators](#generators)

---

## Variables and Data Types 📊

### Basic Data Types
```python
# Integer
x = 10

# Float
pi = 3.14

# String
name = "Python"

# Boolean
is_cool = True

# NoneType
nothing = None
```

### Type Conversion
```python
# Convert to string
str_x = str(x)

# Convert to integer
int_pi = int(pi)

# Convert to float
float_x = float(x)
```

---

## Control Flow 🔄

### If Statements
```python
if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is 5")
else:
    print("x is less than 5")
```

### Loops

#### For Loop
```python
for i in range(5):
    print(i)

# Iterating over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

#### While Loop
```python
count = 5
while count > 0:
    print(count)
    count -= 1
```

#### Break and Continue
```python
for i in range(10):
    if i == 5:
        break  # Exit the loop
    if i % 2 == 0:
        continue  # Skip the rest of the code in this iteration
    print(i)
```

---

## Functions 🛠️

### Defining Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

### Default Arguments
```python
def greet(name="Guest"):
    return f"Hello, {name}!"

print(greet())
```

### Variable-Length Arguments
```python
def add(*args):
    return sum(args)

print(add(1, 2, 3, 4))
```

### Keyword Arguments
```python
def display_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

display_info(name="Alice", age=25)
```

---

## Collections 📚

### Lists
```python
fruits = ["apple", "banana", "cherry"]
fruits.append("date")
print(fruits)

# Accessing elements
print(fruits[1])  # Output: banana

# Slicing
print(fruits[1:3])  # Output: ['banana', 'cherry']
```

### Tuples
```python
coordinates = (10, 20)
print(coordinates)

# Unpacking
x, y = coordinates
print(x, y)
```

### Sets
```python
unique_numbers = {1, 2, 3, 4, 4}
print(unique_numbers)

# Set operations
a = {1, 2, 3}
b = {3, 4, 5}
print(a & b)  # Intersection
print(a | b)  # Union
print(a - b)  # Difference
```

### Dictionaries
```python
person = {"name": "Alice", "age": 25}
print(person["name"])

# Adding and updating
person["city"] = "New York"
person["age"] = 26

# Iterating over keys and values
for key, value in person.items():
    print(f"{key}: {value}")
```

---

## List Comprehensions 📝

```python
# Basic list comprehension
squares = [x**2 for x in range(10)]
print(squares)

# With condition
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(even_squares)
```

---

## File Handling 📂

### Writing to a File
```python
with open("example.txt", "w") as file:
    file.write("Hello, file!")
```

### Reading from a File
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

### Appending to a File
```python
with open("example.txt", "a") as file:
    file.write("\nAppend this line.")
```

### Reading Line by Line
```python
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())  # strip() removes trailing newline
```

---

## Modules and Packages 📦

### Importing Modules
```python
import math
print(math.sqrt(16))

from math import pi
print(pi)
```

### Creating a Module
Create a file `mymodule.py`:
```python
def greet(name):
    return f"Hello, {name}!"
```

Use the module:
```python
import mymodule
print(mymodule.greet("Alice"))
```

### Installing Packages
```sh
pip install requests
```

---

## Error Handling ⚠️

### Try-Except Block
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This will always run.")
```

### Custom Exceptions
```python
class CustomError(Exception):
    pass

try:
    raise CustomError("An error occurred")
except CustomError as e:
    print(e)
```

---

## Classes and Objects 🧩

### Defining a Class
```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return f"{self.name} says woof!"

my_dog = Dog("Rex", 5)
print(my_dog.bark())
```

### Inheritance
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        raise NotImplementedError("Subclass must implement abstract method")

class Dog(Animal):
    def speak(self):
        return f"{self.name} says woof!"

my_dog = Dog("Rex")
print(my_dog.speak())
```

### Class and Static Methods
```python
class MyClass:
    @classmethod
    def class_method(cls):
        return "Class method called"

    @staticmethod
    def static_method():
        return "Static method called"

print(MyClass.class_method())
print(MyClass.static_method())
```

---

## Useful Libraries 📚

### Requests
```python
import requests
response = requests.get("https://api.github.com")
print(response.status_code)
print(response.json())
```

### NumPy
```python
import numpy as np
array = np.array([1, 2, 3, 4])
print(array * 2)

matrix = np.array([[1, 2], [3, 4]])
print(matrix)
print(matrix.T)  # Transpose
```

### Pandas
```python
import pandas as pd
data = {"name": ["Alice", "Bob"], "age": [25, 30]}
df = pd.DataFrame(data)
print(df)

# Basic operations
print(df.describe())
print(df[df["age"] > 25])
```

### Matplotlib
```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [10, 20, 25, 30]

plt.plot(x, y)
plt.xlabel("X axis")
plt.ylabel("Y axis")
plt.title("Simple Plot")
plt.show()
```

### Scikit-Learn
```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Sample data
X = np.array([[1], [2], [3], [4]])
y = np.array([1, 2, 3, 4])

# Create and train the model
model = LinearRegression()
model.fit(X, y)

# Make predictions
predictions = model.predict(np.array([[5]]))
print(predictions)
```

---

## Decorators 🎨

### Function Decorators
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

### Class Decorators
```python
def decorator(cls):
    class Wrapped(cls):
        def __init__(self, *args, **kwargs):
            print("Wrapped class")
            super().__init__(*args, **kwargs)
    return Wrapped

@decorator
class MyClass:
    def __init__(self):
        print("Original class")

instance = MyClass()
```

---

## Generators 🚀

### Generator Function
```python
def countdown

(n):
    while n > 0:
        yield n
        n -= 1

for number in countdown(5):
    print(number)
```

### Generator Expression
```python
squares = (x**2 for x in range(10))
for square in squares:
    print(square)
```
