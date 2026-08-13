🐍 Context Managers in Python

Since you want surface-level understanding, focus on the practical idea rather than advanced internals.

1. What is a Context Manager?

A context manager manages a resource and makes sure it is properly opened and properly closed/released.

The most common syntax is:

with ...:
    ...

Think:

Open resource
     ↓
Use resource
     ↓
Automatically clean up
2. Most common example — files

Without a context manager:

file = open("data.txt")

data = file.read()

file.close()

You have to remember:

file.close()

With a context manager:

with open("data.txt") as file:
    data = file.read()

Python automatically closes the file when the with block finishes.

That's the main reason we use it.

3. Why with?

Suppose an error happens:

file = open("data.txt")

data = file.read()

# something goes wrong here

file.close()

If an exception occurs before close(), the file might not be properly closed.

With:

with open("data.txt") as file:
    data = file.read()

Python handles the cleanup even if an exception occurs.

4. Basic structure
with resource as variable:
    # use resource

Example:

with open("data.txt") as f:
    print(f.read())

Here:

open() → creates the resource
with → manages it
f → gives you access to it
leaving the with block → resource is cleaned up
