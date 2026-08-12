1. Built-in function

A built-in function is a function that Python gives you directly. You don't need to install or import anything.

Examples:

print("Hello")
len([1, 2, 3])
sum([1, 2, 3])
max([10, 20, 5])
type(10)

You can use them immediately.

Examples: print(), len(), sum(), range(), type()

2. Module

A module is basically a .py file containing Python code—functions, classes, variables, etc.

Example:

import math

print(math.sqrt(25))

Here:

math
 ↓
module
 ↓
sqrt()

math is a Python module containing functions such as sqrt(), sin(), cos(), etc.

You can also create your own:

myproject/
    calculator.py
    main.py

calculator.py is a module.

3. Package

A package is a collection/group of related Python modules.

Think:

Package
 ├── module1.py
 ├── module2.py
 └── module3.py

For example, a package can organize functionality into multiple modules.

You might see:

from mypackage import calculator

So:

Module = usually one .py file
Package = collection/organization of modules

4. Library

Library is the broadest term.

A library is a collection of reusable code that you use in your programs. It can contain modules, packages, classes, and functions.

Examples you will encounter:

NumPy
Pandas
Matplotlib
Requests
Scikit-learn

For example:

import numpy as np

arr = np.array([1, 2, 3])

NumPy is commonly called a Python library, and internally it has many modules/packages.

🔥 The easiest way to remember

Imagine a college:

Library
   ↓
Building / organization
   ↓
Package
   ↓
Department
   ↓
Module
   ↓
Individual file
   ↓
Function

And separately:

Built-in function
   ↓
Python already provides it
   ↓
print()
len()
sum()
Quick comparison
Term	What it is	Example
Built-in function	Individual function provided directly by Python	len()
Module	Python file containing code	math
Package	Collection/organization of modules	mypackage
Library	Broad collection of reusable code	NumPy
