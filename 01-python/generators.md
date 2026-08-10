Generators in Python
1. Why do we need generators?

Suppose you want numbers from 1 to 5.

Normal approach:

numbers = [1, 2, 3, 4, 5]

for n in numbers:
    print(n)

The entire list is stored in memory.

With a generator:

def numbers():
    for i in range(1, 6):
        yield i

Now:

for n in numbers():
    print(n)

Output:

1
2
3
4
5

The important difference is that the generator produces one value at a time instead of creating all values at once.

2. yield — the most important part

A normal function uses return:

def test():
    return 10

Once return executes, the function ends.

A generator uses yield:

def test():
    yield 10
    yield 20
    yield 30

Calling it:

x = test()

print(x)

doesn't directly give 10.

It gives a generator object.

<generator object test at ...>

To get values:

print(next(x))
print(next(x))
print(next(x))

Output:

10
20
30
3. How yield works

This is the most important concept.

def test():
    print("A")
    yield 10

    print("B")
    yield 20

    print("C")
    yield 30

Now:

x = test()

print(next(x))
print(next(x))
print(next(x))

Output:

A
10
B
20
C
30

Notice:

First next()

Python runs:

print("A")
yield 10

Then pauses the function.

Second next()

Python continues from where it stopped:

print("B")
yield 20

Then pauses again.

That's the magic of generators.

4. yield vs return

Remember this simple table:

return	yield
Ends function	Pauses function
Gives one final result	Can produce many values
Function starts again if called again	Continues from previous position
Normal function	Generator function

Example:

def normal():
    return 1
    return 2

Only:

1

But:

def generator():
    yield 1
    yield 2

Can produce:

1
2
5. Generator with a loop

This is the most common pattern.

def numbers(n):
    for i in range(1, n + 1):
        yield i

Use:

for x in numbers(5):
    print(x)

Output:

1
2
3
4
5

Behind the scenes:

yield 1
   ↓
pause
   ↓
yield 2
   ↓
pause
   ↓
yield 3
   ↓
9. Generator expression

You can also create generators without writing a function.

List comprehension:

numbers = [x * 2 for x in range(5)]

This creates a list.

Generator expression:

numbers = (x * 2 for x in range(5))

This creates a generator.

Compare:

[x * 2 for x in range(5)]

vs

(x * 2 for x in range(5))

Square brackets → list

Parentheses → generator expression

Example:

g = (x * 2 for x in range(5))

print(next(g))
print(next(g))

Output:

0
2

. Generator vs Iterator

You can remember it like this:

Creating an iterator manually
class Numbers:
    def __iter__(self):
        return self

    def __next__(self):
        ...

More code.

Creating an iterator using generator
def numbers():
    yield 1
    yield 2
    yield 3

Much simpler.

Generator = easy way to create iterators.
