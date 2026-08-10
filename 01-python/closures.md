
CLOSURES

1. First, what is a closure?

A closure happens when:

An inner function remembers and uses a variable from its outer function, even after the outer function has finished.

That's the main definition you need.

2. Simple example
def outer():
    x = 10

    def inner():
        print(x)

    return inner

Now:

func = outer()
func()

Output:

10
What happened?
outer()
   ↓
x = 10
   ↓
inner() created
   ↓
inner returned
   ↓
outer() finished
   ↓
func still remembers x = 10

That remembering is the important part of a closure.

3. Why is it called a closure?

Look at this:

def outer():
    message = "Hello"

    def inner():
        print(message)

    return inner

When you do:

f = outer()

outer() has finished.

Normally, you might think message is gone.

But:

f()

still prints:

Hello

The inner function closed over the message variable.

Hence:

Closure = inner function + remembered outer variables

Closure vs normal nested function

Nested function:

def outer():
    x = 10

    def inner():
        print(x)

This alone isn't necessarily what you need to call a closure.

The important part is that the inner function captures/remembers the outer variable, and typically the inner function is returned or otherwise escapes the outer function.

Example:

def outer():
    x = 10

    def inner():
        print(x)

    return inner

5. Closures and decorators 🔥

This is especially important for you because you've already learned decorators.

Decorators commonly use:

Outer function
      ↓
Inner function
      ↓
Closure

Example:

def decorator(func):

    def wrapper():
        print("Before")
        func()
        print("After")

    return wrapper

Here wrapper() remembers func.

That's a closure.

So your previous decorators knowledge + closures are directly connected.
