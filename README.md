
# Python Cheat Sheet

## Table of Contents
1. [Basics](#1-basics)
2. [Operators](#2-operators)
3. [Control Flow](#3-control-flow)
4. [Functions](#4-functions)
5. [Data Structures](#5-data-structures)
    - [Strings](#strings)
    - [Lists](#lists)
    - [Slicing Lists](#slicing-lists)
    - [Dictionaries](#dictionaries)
    - [Dictionary Iteration](#dictionary-iteration)
    - [Tuples](#tuples)
    - [Sets](#sets)
6. [Common Built-in Functions](#6-common-built-in-functions)
7. [Modules and Imports](#7-modules-and-imports)


## 1. Basics

### Variables and Data Types
```python
# Variables
x = 1  # Integer
y = 1.5  # Float
name = "Kai"  # String
is_male = True  # Boolean

# Check types
type(x)  # <class 'int'>
```

### Data Type Conversion
```python
int(2.5)  # 2
float(5)  # 5.0
str(100)  # '100'
bool(0)  # False
bool(10)  # True: should be true for any non 0 number both positive and negative
```

## 2. Operators

### Arithmetic
```python
a = 10 + 5  # Addition
b = 10 - 5  # Subtraction
c = 10 * 5  # Multiplication
d = 10 / 5  # Division (always returns float)
e = 10 // 3  # Floor division (will return integer)
f = 10 % 3  # Modulo (find the remainder)
g = 2 ** 3  # Exponentiation (2 to the power of 3 in this example)
```

### Comparison
```python
1 == 2  # False
1 != 2  # True
1 > 2  # False
1 <= 2  # True
```

### Logical
```python
True and False  # False
True or False  # True
not True  # False
```

## 3. Control Flow

### If/Else Statements
```python
if x > 0:
    print("x is greater than 0")
elif x == 0:
    print("x is equal to 0")
else:
    print("x is less than 0")
```

### Loops
```python
# While Loop
count = 0
while count < 5:
    print(count)
    count += 1

# For Loop using a range
for i in range(5):  
    print(i) # 0, 1, 2, 3, 4

# Looping through a list
cities = ["Amsterdam", "Leeuwarden", "Den Haag", "Arnhem"]
for city in cities:
    print(cities)

# Looping through a list with index using enumarate
cities = ["Amsterdam", "Leeuwarden", "Den Haag", "Arnhem"]
for index, city in enumerate(cities):
     print(f"{index}: {city}")

# Looping through multiple lists using zip
fruits = ["apple", "banana", "mango"]
prices = [5, 4.50, 7]
for fruit, price in zip(fruits, prices):
    print(f"{fruit} cost €{price}.")

# Exiting loop early using break:
for i in range(5):
    if i == 3:
        break  # Exits loop when i is 3
    print(i)    
```


### List Comprehension
```python
doubled = [x*2 for x in range(5)]  # [0, 2, 4, 6, 8]
```

## 4. Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Kai"))  # Output: Hello, Kai!
```

## 5. Data Structures

### Strings
```python

# Removing whitespaces:
to_strip = "  Hello, Kai!  "
to_strip.strip()  # "Hello, Kai!" (Removes both leading and trailing spaces)
to_strip.lstrip()  # "Hello, Kai!  " (Removes leading spaces)
to_strip.rstrip()  # "  Hello, Kai!" (Removes trailing spaces)

# Changing case:
my_string = "Hello, Kai!"
my_string.lower()  # "  hello, kai!  " (Converts to lowercase)
my_string.upper()  # "  HELLO, KAI!  " (Converts to uppercase)

my_string2 = "hello, kai!"
my_string2.capitalize()  # "Hello, kai!" (Capitalizes the first letter of the string)

# Finding Substrings:
my_string.find("Kai")  # 7 (Returns the index of the first occurrence of a substring)

my_string3 = "Hello, Kai! Hello, Kai!"
my_string3.count("Kai")  # 2 (Counts the number of occurrences of a substring)

my_string.replace("Kai", "World")  # "Hello, World!" (original was "Hello, Kai!")

# String Splitting and Joining:
my_string4 = "apple,banana,mango"
# (Splits a string into a list based on a delimiter, in this case a ',')
my_string4.split(",")  # ['apple', 'banana', 'mango'] (string to list)

fruits = ['apple', 'banana', 'mango']
# (Joins elements of a list into a string with a delimiter, in this case with a ', ')
my_string = ", ".join(fruits)  # "apple, banana, mango" (list to string)

# Checking String Contents:
my_string.startswith("Hello")  # True
my_string.endswith("Kai!")  # True
```

### Lists
```python
# Create a list
my_list = [1, 2, 3, 4, 5]

# Access elements
my_list[0]  # 1
my_list[-1]  # 5 (last element)
my_list[-2]  # 4 (second to last element)

# Modify elements
my_list[1] = 10

# Reverse list
my_list[::-1]

# List methods
my_list.append(6)  # Add element
my_list.remove(10)  # Remove element "10" not the element in index 10
my_list.pop() # Removes the last element
del my_list[2]  # Removes element at index 2 (3)
```

#### **Slicing Lists**

Slicing is used to access a portion (sublist) of a list. You can specify a range of indices to create a new list or to modify an existing list.

##### **Syntax:**
```python
list[start:end:step]
```
- `start`: Index to start the slice (inclusive).
- `end`: Index to end the slice (exclusive).
- `step`: (Optional) The increment between each index.


##### **Examples:**
```python
1. Basic Slicing

my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[2:5]  # Gets elements at indices 2, 3, 4 (values 3, 4, 5)

print(sublist)  # Output: [3, 4, 5]

2. Slicing with Start Only
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[2:]  # Gets elements starting at index 2 until the end of the list

print(sublist)  # Output: [3, 4, 5, 6, 7]

3. Slicing with End Only
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[:4]  # Gets elements from the start up to index 4 (exclusive)

print(sublist)  # Output: [1, 2, 3, 4]

4. Slicing with Step
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[0:7:2]  # Gets every second element

print(sublist)  # Output: [1, 3, 5, 7]

5. Negative Indices
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[-4:-1]  # Gets elements at indices -4, -3, -2 (values 4, 5, 6)
print(sublist)  # Output: [4, 5, 6]

6. Removing a Sublist
You can remove a range of elements from a list using the `del` statement:
my_list = [1, 2, 3, 4, 5, 6, 7]
del my_list[2:5]  # Removes elements at indices 2, 3, and 4 (values 3, 4, 5)

print(my_list)  # Output: [1, 2, 6, 7]
```


### Dictionaries
```python
# Create a dictionary
my_dict = {"name": "Kai", "profession": "Software Engineer"}

# Access values
my_dict["name"]  # Kai

# Add or modify values
my_dict["city"] = "Amsterdam"

# Dictionary methods
my_dict.keys()  # dict_keys(['name', 'profession', 'city'])
my_dict.values()  # dict_values(['Kai', 'Software Engineer', 'Amsterdam'])
```

#### Dictionary Iteration
```python
my_dict = {"name": "Kai", "profession": "Software Engineer"}

for key in my_dict:
    print(key)

for value in my_dict.values():
    print(value)

for key, value in my_dict.items():
    print(f"{key}: {value}")
```

### Tuples
What is the difference between a *tuple* and a *list*? 
A *list* is mutable, meaning you can add, remove, or change the elements that are definied in it.
A *tuple* is immutable, meaning that once defined, you cannot add, remove, or change the elements defined in it.

```python
# Create a tuple
my_tuple = (1, 2, 3)

# Access elements 
my_tuple[0]  # 1

# Modify element
my_tuple[1] = 10 # Not allowed, will output a type error: 'tuple' object does not support item assignment


```

### Sets
```python
# Creating a set
cities = {'Amsterdam', 'Rotterdam', 'The Hague', 'Amsterdam', 'Utrecht'}  # Initial set with duplicates

# Adding an element
cities.add('Eindhoven')

# Removing an element
cities.remove('Rotterdam')

# Checking membership
'Amsterdam' in cities  # Returns True

# Set operations
set_a = {'Amsterdam', 'Rotterdam', 'The Hague'}
set_b = {'Rotterdam', 'Utrecht'}
print(set_a | set_b)  # Union: {'Amsterdam', 'Rotterdam', 'The Hague', 'Utrecht'}
print(set_a & set_b)  # Intersection: {'Rotterdam'}
```


## 6. Common Built-in Functions
```python
len([1, 2, 3])  # 3
max([1, 2, 3])  # 3
min([1, 2, 3])  # 1
sum([1, 2, 3])  # 6
sorted([3, 1, 2])  # [1, 2, 3]
```


## 7. Modules and Imports
```python
# Import a module
import math
print(math.sqrt(16))  # 4.0

# Import specific function
from math import pi
print(pi)  # 3.141592653589793
```
