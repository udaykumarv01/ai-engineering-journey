2. Comprehensions

Comprehensions are a short way to create collections such as lists, sets, and dictionaries.

1. List Comprehension

Normal way:

squares = []

for i in range(1, 6):
    squares.append(i * i)

print(squares)

Output:

[1, 4, 9, 16, 25]

Using comprehension:

squares = [i * i for i in range(1, 6)]

print(squares)

Output:

[1, 4, 9, 16, 25]
Syntax
[expression for item in iterable]

Think:

[what you want  for  each item  in  collection]
2. List Comprehension with Condition

Get only even numbers:

even = [x for x in range(1, 11) if x % 2 == 0]

print(even)

Output:

[2, 4, 6, 8, 10]

Syntax:

[expression for item in iterable if condition]

4. String Example
names = ["uday", "rahul", "anil"]

upper_names = [name.upper() for name in names]

print(upper_names)

Output:

['UDAY', 'RAHUL', 'ANIL']

5. If-Else in Comprehension
numbers = [1, 2, 3, 4, 5]

result = ["Even" if x % 2 == 0 else "Odd" for x in numbers]

print(result)

Output:

['Odd', 'Even', 'Odd', 'Even', 'Odd']

Notice the difference:

Only if:

[x for x in numbers if x > 5]

if-else:

["Yes" if x > 5 else "No" for x in numbers]
6. Set Comprehension

Same idea, but creates a set:

numbers = [1, 2, 2, 3, 3, 4]

result = {x * 2 for x in numbers}

print(result)

Output:

{2, 4, 6, 8}

Duplicates are removed because it is a set.

7. Dictionary Comprehension
numbers = [1, 2, 3, 4]

squares = {x: x * x for x in numbers}

print(squares)

Output:

{1: 1, 2: 4, 3: 9, 4: 16}

Syntax:

{key: value for item in iterable}
Why Comprehensions Are Important

You'll use them frequently in:

Data processing
Python projects
AI/ML code
DSA
Converting lists
Filtering data
Creating dictionaries quickly
Most Important Patterns
# List
[x * 2 for x in numbers]

# List + condition
[x for x in numbers if x % 2 == 0]

# List + if/else
["Even" if x % 2 == 0 else "Odd" for x in numbers]

# Set
{x * 2 for x in numbers}

# Dictionary
{x: x * x for x in numbers}
