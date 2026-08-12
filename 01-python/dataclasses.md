Dataclasses in Python

Dataclasses are mainly a convenient way to create classes that store data.

They reduce the amount of boilerplate code you have to write.

1. Normal class

Without dataclass:

class Student:

    def __init__(self, name, age, branch):
        self.name = name
        self.age = age
        self.branch = branch

Then:

s = Student("Uday", 18, "CSE")

print(s.name)
print(s.age)

You had to manually write __init__().

2. Using @dataclass
from dataclasses import dataclass

@dataclass
class Student:
    name: str
    age: int
    branch: str

Now:

s = Student("Uday", 18, "CSE")

print(s.name)
print(s.age)

That's it.

The dataclass automatically creates an appropriate __init__() for you.

3.Default values

You can give a default:

from dataclasses import dataclass

@dataclass
class Student:
    name: str
    age: int = 18

Now:

s = Student("Uday")

print(s)

Output:

Student(name='Uday', age=18)

Main benefits:
Less boilerplate code
Automatically generates __init__
Gives useful representation of objects
Can handle equality and other common methods
Type annotations are normally used with it
One-line definition:

A dataclass is a Python class designed to make storing and managing data simpler with less boilerplate code.
