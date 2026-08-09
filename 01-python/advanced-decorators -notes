1️⃣ Functions are objects

In Python, a function can be stored in a variable.

def greet():
    print("Hello")

x = greet

x()
Output
Hello

Why?

Normally:

greet()

means run the function.

But:

x = greet

means give the function to x.

So:

greet
  ↓
  x
  ↓
x()
  ↓
Hello

⚠️ Notice:

x = greet

not:

x = greet()

Because greet() runs the function immediately.

2️⃣ Passing a function as an argument

A function can be given to another function.

def greet():
    print("Hello")

def execute(func):
    func()

execute(greet)
Output
Hello

Here:

execute(greet)

means:

"Give the greet function to execute."

Inside execute:

func()

runs greet().

Simple picture
greet()
  ↑
  |
execute(greet)
  |
  ↓
func()

This concept is very important for decorators.

3️⃣ Returning a function

A function can also return another function.

def outer():

    def inner():
        print("Hello")

    return inner

Now:

x = outer()

x()

Output:

Hello

What happened?

outer()
   ↓
returns inner
   ↓
x = inner
   ↓
x()
   ↓
Hello

So remember:

A function can return another function.

4️⃣ Higher-order functions

Now combine what we learned.

A function is called a higher-order function when it:

accepts another function, OR
returns another function.

Example:

def execute(func):
    func()

execute accepts a function.

Another:

def outer():

    def inner():
        print("Hello")

    return inner

outer returns a function.

You don't need to memorize the terminology too much. Just understand the behavior.

5️⃣ Now comes the decorator

Suppose we have:

def greet():
    print("Hello")

We want:

Before
Hello
After

without changing greet() itself.

We create:

def decorator(func):

    def wrapper():
        print("Before")

        func()

        print("After")

    return wrapper

Then:

greet = decorator(greet)

Now:

greet()

Output:

Before
Hello
After
What's happening?

Originally:

greet → original function

After:

greet = decorator(greet)

it becomes:

greet → wrapper

And wrapper contains:

func()

which runs the original greet.

6️⃣ @decorator

Python gives us a shortcut.

Instead of:

def greet():
    print("Hello")

greet = decorator(greet)

we can write:

@decorator
def greet():
    print("Hello")

These two are exactly equivalent.

@decorator
def greet():
    print("Hello")

means:

def greet():
    print("Hello")

greet = decorator(greet)

🔥 This is the most important decorator rule.

7️⃣ Decorators with arguments

Consider:

def add(a, b):
    return a + b

Our previous wrapper:

def wrapper():

can't receive a and b.

So we use:

def wrapper(*args, **kwargs):

Example:

def decorator(func):

    def wrapper(*args, **kwargs):
        print("Before")

        result = func(*args, **kwargs)

        print("After")

        return result

    return wrapper

Then:

@decorator
def add(a, b):
    return a + b

Call:

print(add(10, 20))

Output:

Before
After
30
What are *args and **kwargs?

For now, simply remember:

*args

handles normal positional arguments:

add(10, 20)

and:

**kwargs

handles named arguments:

student(name="Uday", age=18)

So this:

wrapper(*args, **kwargs)

makes our decorator flexible.

8️⃣ Why return result?

Look at:

def add(a, b):
    return a + b

It returns:

30

But if our decorator does:

def wrapper(*args, **kwargs):
    func(*args, **kwargs)

the result isn't returned by the wrapper.

So we do:

result = func(*args, **kwargs)

return result

This preserves the original function's return value.

9️⃣ @wraps

Sometimes decorators hide the original function's name.

For example:

def decorator(func):

    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)

    return wrapper

Python may now see the function as:

wrapper

instead of:

add

So we use:

from functools import wraps

and:

@wraps(func)

Example:

from functools import wraps

def decorator(func):

    @wraps(func)
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)

    return wrapper

This preserves information such as:

add.__name__
🔟 Decorator with its own argument

This is more advanced.

You may see:

@repeat(3)
def hello():
    print("Hello")

Here repeat itself receives 3.

The structure becomes:

def repeat(times):

    def decorator(func):

        def wrapper(*args, **kwargs):

            for i in range(times):
                func(*args, **kwargs)

        return wrapper

    return decorator

Then:

@repeat(3)
def hello():
    print("Hello")

Output:

Hello
Hello
Hello

Don't worry if this looks confusing now. Understand the first 9 concepts before trying to memorize this.

1️⃣1️⃣ Multiple decorators

You can put decorators together:

@decorator1
@decorator2
def hello():
    print("Hello")

This is equivalent to:

hello = decorator1(decorator2(hello))

So the bottom decorator is applied first.

1️⃣2️⃣ Built-in decorators

Later you'll encounter:

@staticmethod
class Student:

    @staticmethod
    def hello():
        print("Hello")
@classmethod
class Student:

    @classmethod
    def show(cls):
        print("Hello")
@property
class Student:

    @property
    def name(self):
        return "Uday"

These are all based on the same general idea: a decorator modifies how a method/function behaves.

🧠 Your learning order

Don't study all of them at once. Follow this:

1. Functions
      ↓
2. Functions stored in variables
      ↓
3. Functions passed as arguments
      ↓
4. Functions returned from functions
      ↓
5. Higher-order functions
      ↓
6. Basic decorator
      ↓
7. @decorator
      ↓
8. *args and **kwargs
      ↓
9. return result
      ↓
10. functools.wraps
      ↓
11. Multiple decorators
      ↓
12. Decorators with arguments
      ↓
13. Built-in decorators
🎯 Most important for you

Since you're learning Python for AI engineering, don't move ahead until you can explain this:

def decorator(func):

    def wrapper(*args, **kwargs):
        print("Before")
        result = func(*args, **kwargs)
        print("After")
        return result

    return wrapper

in your own words.

Next, start with #1 only: functions as objects. Once that is crystal clear, everything else becomes much easier.
