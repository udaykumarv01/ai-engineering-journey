Dunder Methods in Python

You only need the important surface-level concepts for now.

1. What are Dunder Methods?

Dunder = Double UNDERscore

Methods that start and end with __:

__init__
__str__
__len__
__add__

They are special methods that tell Python how your objects should behave.

2. __init__() — Most important ⭐

You probably already know this one.

class Student:

    def __init__(self, name, age):
        self.name = name
        self.age = age

When you do:

s = Student("Uday", 18)

Python automatically calls:

__init__()

So:

Student(...)
     ↓
__init__()
     ↓
object created with data
3. __str__() — Control print()

Suppose:

class Student:

    def __init__(self, name):
        self.name = name
s = Student("Uday")

print(s)

Without __str__(), Python gives something like:

<__main__.Student object at 0x...>

Not very useful.

Add:

class Student:

    def __init__(self, name):
        self.name = name

    def __str__(self):
        return self.name

Now:

print(s)

Output:

Uday

So remember:

__str__() controls what you see when you print(object).

4. __len__() — Control len()
class Team:

    def __init__(self, players):
        self.players = players

    def __len__(self):
        return len(self.players)

Now:

team = Team(["A", "B", "C"])

print(len(team))

Output:

3

Python sees:

len(team)

and internally uses:

team.__len__()
5. __add__() — Control +

Normally:

5 + 3

means addition.

But you can define what + means for your own objects.

class Number:

    def __init__(self, value):
        self.value = value

    def __add__(self, other):
        return Number(self.value + other.value)

Now:

a = Number(10)
b = Number(20)

c = a + b

print(c.value)

Output:

30

So:

a + b
 ↓
a.__add__(b)
6. Other important dunder methods

You don't need to memorize all of them.

Just recognize these:

Dunder	Used for
__init__()	Initialize object
__str__()	print(object)
__len__()	len(object)
__add__()	object + object
__eq__()	object == object
__lt__()	object < object
__enter__()	with starts
__exit__()	with ends
