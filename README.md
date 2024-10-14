
# Python Cheat Sheet

## Table of Contents
1. [Basics](#1-basics)
    - 1.1 [Variables and Data Types](#11-variables-and-data-types)
    - 1.2 [Data Type Conversion](#12-data-type-conversion)
2. [Operators](#2-operators)
    - 2.1 [Arithmetic](#21-arithmetic)
    - 2.2 [Comparison](#22-comparison)
    - 2.3 [Logical](#23-logical)
3. [Strings](#3-strings)
    - 3.1 [String Methods](#31-string-methods)
    - 3.1 [Slicing Strings](#32-slicing-strings)
4. [Control Flow](#4-control-flow)
    - 4.1 [If / Else Statements](#41-ifelse-statements)
    - 4.2 [Loops](#42-loops)
    - 4.3 [List Comprehension](#43-list-comprehension)
5. [Functions](#5-functions)
6. [Data Structures](#5-data-structures)
    - 6.1 [Lists](#61-lists)
        - 6.1.1 [List Methods](#611-list-methods)
        - 6.1.2 [Slicing Lists](#612-slicing-lists)
    - 6.2 [Dictionaries](#53-dictionaries)
        - 6.2.1 [Dictionary Methods](#621-dictionary-methods)
        - 6.2.2 [Dictionary Iteration](#622-dictionary-iteration)
    - 6.3 [Tuples](#54-tuples)
    - 6.4 [Sets](#55-sets)
7. [Modules and Imports](#6-modules-and-imports)
8. [Error Handling](#8-error-handling)


## 1. Basics

### 1.1 Variables and Data Types
```python
# Variables
x = 1  # Integer
y = 1.5  # Float
name = "Kai"  # String
is_male = True  # Boolean

# Check types
type(x)  # <class 'int'>
```

### 1.2 Data Type Conversion
```python
int(2.5)  # 2
float(5)  # 5.0
str(100)  # '100'
bool(0)  # False
bool(10)  # True: should be true for any non 0 number both positive and negative
```

## 2. Operators

### 2.1 Arithmetic
```python
a = 10 + 5  # Addition
b = 10 - 5  # Subtraction
c = 10 * 5  # Multiplication
d = 10 / 5  # Division (always returns float)
e = 10 // 3  # Floor division (will return integer)
f = 10 % 3  # Modulo (find the remainder)
g = 2 ** 3  # Exponentiation (2 to the power of 3 in this example)
```

### 2.2 Comparison
```python
1 == 2  # False
1 != 2  # True
1 > 2  # False
1 <= 2  # True
```

### 2.3 Logical
```python
True and False  # False
True or False  # True
not True  # False
```

## 3. Strings

### 3.1 String Methods
```python
my_string = "Hello, Kai!"

# Length of a String:
len(my_string)  # 11

# Reversing a String
my_string[::-1]  # "!iaK ,olleH"

# Changing case:
my_string.lower()  # "hello, kai!" (Converts to lowercase)
my_string.upper()  # "HELLO, KAI!" (Converts to uppercase)

my_string2 = "hello, kai!"
my_string2.capitalize()  # "Hello, kai!" (Capitalizes the first letter of the string)
my_string2.title()  # "Hello, Kai!" (Converts the first character of each word to uppercase)

# Finding Substrings:
my_string.find("Kai")  # 7 (Returns the index of the first occurrence of a substring)
my_string.index("Kai") # 7 (Returns the index of the first occurrence (same as find))

# Finding Substrings with start and end parameters
my_string.index("o", 0, 5)  # 4 (Searches for "o" only between index 0 (inclusive) and 5(exclusive))

# Replacing Substrings:
my_string.replace("Kai", "World")  # "Hello, World!" (original was "Hello, Kai!")

# String Splitting and Joining:
my_string4 = "apple,banana,mango"
# (Splits a string into a list based on a delimiter, in this case a ',')
my_string4.split(",")  # ['apple', 'banana', 'mango'] (string to list)

fruits = ['apple', 'banana', 'mango']
# (Joins elements of a list into a string with a delimiter, in this case with a ', ')
my_string = ", ".join(fruits)  # "apple, banana, mango" (list to string)

# Check String Contents:
my_string.startswith("Hello")  # True
my_string.endswith("Kai!")  # True
"abcdef123".isalnum()  # True if all characters are letters and numbers only. no space or special characters 
"333".isdigit()  # True if all characters are digits. no space or special characters.
"abc".isalpha()  # True if all characters must be latin letters. no space, numbers, or special characters)
"   ".isspace()  # True if all characters must be spaces)

# Checking for Lowercase and Uppercase
"hello".islower()  # True
"HELLO".isupper()  # True

# Removing whitespaces:
to_strip = "  Hello, Kai!  "
to_strip.strip()  # "Hello, Kai!" (Removes both leading and trailing spaces)
to_strip.lstrip()  # "Hello, Kai!  " (Removes leading spaces)
to_strip.rstrip()  # "  Hello, Kai!" (Removes trailing spaces)

# Counting Substrings:
my_string3 = "Hello, Kai! Hello, Kai!"
my_string3.count("Kai")  # 2 (Counts the number of occurrences of a substring)
```

### 3.2 Slicing Strings

Slicing is used to access a portion of a string (substring). You can specify a range of indices to create a new substring without modifying the original string. The slice includes characters from the starting index up to (but not including) the ending index.

**Syntax:**
```python
string[start:end:step]
```
- `start`: Index to start the slice (inclusive).
- `end`: Index to end the slice (exclusive).
- `step`: (Optional) The increment between each index.

```python
# Basic Slicing
sliced_string = "Hello, Kai!"[0:5]  # Gets characters from index 0 to 4 (inclusive)
print(sliced_string)  # Output: "Hello"

# Slicing with Start Only
sliced_string = "Hello, Kai!"[7:]  # Gets characters from index 7 to the end
print(sliced_string)  # Output: "Kai!"

# Slicing with End Only
sliced_string = "Hello, Kai!"[:5]  # Gets characters from the start to index 5 (exclusive)
print(sliced_string)  # Output: "Hello"

# Slicing with Step
sliced_string = "Hello, Kai!"[::2]  # Gets every second character
print(sliced_string)  # Output: "Hlo ai!"

# Negative Indices
sliced_string = "Hello, Kai!"[-5:]  # Gets the last 5 characters
print(sliced_string)  # Output: "Kai!"
```

## 4. Control Flow

### 4.1 If/Else Statements
```python
if x > 0:
    print("x is greater than 0")
elif x == 0:
    print("x is equal to 0")
else:
    print("x is less than 0")
```

### 4.2 Loops
```python
# While Loop
count = 0
while count < 5:
    print(count)
    count += 1

# For Loop using a range
for i in range(5):  
    print(i) # Output: 0, 1, 2, 3, 4

# Looping through a list
cities = ["Amsterdam", "Leeuwarden", "Den Haag", "Arnhem"]
for city in cities:
    print(city) # Output: Each city in the list

# Looping through a list with index using enumarate
cities = ["Amsterdam", "Leeuwarden", "Den Haag", "Arnhem"]
for index, city in enumerate(cities):
     print(f"{index}: {city}")  # Output: 0: Amsterdam, 1: Leeuwarden, etc.

# Looping through multiple lists using zip
fruits = ["apple", "banana", "mango"]
prices = [5, 4.50, 7]
for fruit, price in zip(fruits, prices):
    print(f"{fruit} cost €{price}.") # Output: apple cost €5, etc.

# Looping through a string
my_string = "Amsterdam"
for i in my_string:
    print(i) #Output: A, m, s, t, e, r, d, a, m

# Exiting loop early using break:
for i in range(5):
    if i == 3:
        break  # Exits loop when i is 3
    print(i)    
```

### 4.3 List Comprehension
```python
doubled = [x*2 for x in range(5)]  # [0, 2, 4, 6, 8]

# List comprehension with condition
even_numbers = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

## 5. Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Kai"))  # Output: Hello, Kai!
```

## 6. Data Structures

### 6.1 Lists

#### 6.1.1 List Methods
```python
# Create a list
my_list = [1, 2, 3, 4, 5]

# Access elements
my_list[0]  # 1 
my_list[-1]  # 5 (last element)
my_list[-2]  # 4 (second to last element)

# Modify elements
my_list[1] = 10

# List methods
my_list.append(6)  # Add element to the end of the list
my_list.remove(10)  # Remove element "10" not the element in index 10
my_list.pop() # Removes and returns the last element from the list
del my_list[2]  # Removes element at index 2 (3)
my_list.extend([7, 8])  # Extends the list by appending elements from another list
my_list.sort()  # Sorts the list in ascending order

# Reverse list
my_list[::-1] # Output [5, 4, 3, 2, 1]

# Built-in Functions
len(my_list)  # will return the length of 5
max(my_list)  # 5
min(my_list)  # 1
sum(my_list)  # will sum the total of all the elements of a list, in this case, 15
sum([1, 2, 'three', 4, 5]) # will return a TypeError, sum requires numeric arguments
sorted([3, 1, 2])  # Returns a new sorted list: Output: [1, 2, 3] 
```

#### 6.1.2 Slicing Lists

Slicing is used to access a portion (sublist) of a list. You can specify a range of indices to create a new list or to modify an existing list.

**Syntax:**
```python
list[start:end:step]
```
- `start`: Index to start the slice (inclusive).
- `end`: Index to end the slice (exclusive).
- `step`: (Optional) The increment between each index.

```python
# Basic Slicing
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[2:5]  # Gets elements at indices 2, 3, 4 (values 3, 4, 5)
print(sublist)  # Output: [3, 4, 5]

# Slicing with Start Only
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[2:]  # Gets elements starting at index 2 until the end of the list
print(sublist)  # Output: [3, 4, 5, 6, 7]

# Slicing with End Only
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[:4]  # Gets elements from the start up to index 4 (exclusive)
print(sublist)  # Output: [1, 2, 3, 4]

# Slicing with Step
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[0:7:2]  # Gets every second element
print(sublist)  # Output: [1, 3, 5, 7]

# Negative Indices
my_list = [1, 2, 3, 4, 5, 6, 7]
sublist = my_list[-4:-1]  # Gets elements at indices -4, -3, -2 (values 4, 5, 6)
print(sublist)  # Output: [4, 5, 6]

# Removing a Sublist
# You can remove a range of elements from a list using the `del` statement:
my_list = [1, 2, 3, 4, 5, 6, 7]
del my_list[2:5]  # Removes elements at indices 2, 3, and 4 (values 3, 4, 5)
print(my_list)  # Output: [1, 2, 6, 7]
```


### 6.2 Dictionaries

#### 6.2.1 Dictionary Methods
```python
# Create a dictionary
my_dict = {"name": "Kai", "profession": "Software Engineer"}

# Access values
my_dict["name"]  # Output: Kai

# Add or modify values
my_dict["city"] = "Amsterdam" # if the key exists, then the value will be overwritten

# Dictionary methods
my_dict.keys()  # dict_keys(['name', 'profession', 'city'])
my_dict.values()  # dict_values(['Kai', 'Software Engineer', 'Amsterdam'])
```

#### 6.2.2 Dictionary Iteration
```python
my_dict = {"name": "Kai", "profession": "Software Engineer"}

for key in my_dict:
    print(key)

for value in my_dict.values():
    print(value)

for key, value in my_dict.items():
    print(f"{key}: {value}")
```

### 6.3 Tuples
What is the difference between a *list* and a *tuple*? 

A *list* is mutable, meaning you can add, remove, or change the elements that are definied in it.
A *tuple* is immutable, meaning that once defined, you cannot add, remove, or change the elements defined in it.

```python
# Create a tuple
my_tuple = (1, 2, 3)

# Access elements 
my_tuple[0]  # 1

# Modify element
my_tuple[1] = 10 # Raises TypeError: 'tuple' object does not support item assignment


```

### 6.4 Sets
```python
# Creating a set
cities = {'Amsterdam', 'Rotterdam', 'The Hague', 'Amsterdam', 'Utrecht'} # 'Amsterdam' will only appear once

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

## 7. Modules and Imports
```python
# Import a module
import math
print(math.sqrt(16))  # 4.0

# Import specific function
from math import pi
print(pi)  # 3.141592653589793

# Renaming imported module with 'as' 
import numpy as np
```

## 8. Error Handling
Error handling in Python is done using try and except blocks, allowing you to manage exceptions that may occur during program execution.

```python
try:
    # Code that may raise an error
    result = 10 / 0
except ZeroDivisionError:
    print("You can't divide by zero!")
```