# Lambda Functions in Python

## What is a Lambda Function?

A **lambda function** is a small anonymous function used for simple operations.

### Syntax

```python
lambda arguments: expression
```

### Example

```python
square = lambda x: x * x

print(square(5))
```

Output:

```text
25
```

The lambda function:

```python
lambda x: x * x
```

takes `x` as input and returns `x * x`.

---

## Lambda with Multiple Arguments

```python
add = lambda a, b: a + b

print(add(10, 20))
```

Output:

```text
30
```

---

## Lambda with Condition

```python
check = lambda x: "Even" if x % 2 == 0 else "Odd"

print(check(5))
```

Output:

```text
Odd
```

---

## Common Applications

### 1. Using `map()`

Applies a function to every element.

```python
numbers = [1, 2, 3, 4]

result = list(map(lambda x: x * 2, numbers))

print(result)
```

Output:

```text
[2, 4, 6, 8]
```

### 2. Using `filter()`

Selects elements based on a condition.

```python
numbers = [1, 2, 3, 4, 5, 6]

result = list(filter(lambda x: x % 2 == 0, numbers))

print(result)
```

Output:

```text
[2, 4, 6]
```

### 3. Using `sorted()`

Useful for custom sorting.

```python
students = [
    ("Uday", 85),
    ("Rahul", 92),
    ("Anil", 78)
]

students.sort(key=lambda x: x[1])

print(students)
```

Output:

```text
[('Anil', 78), ('Uday', 85), ('Rahul', 92)]
```

### 4. Using `max()` and `min()`

```python
students = [
    ("Uday", 85),
    ("Rahul", 92),
    ("Anil", 78)
]

highest = max(students, key=lambda x: x[1])
lowest = min(students, key=lambda x: x[1])
```

---

## Lambda vs Normal Function

Normal function:

```python
def square(x):
    return x * x
```

Lambda:

```python
square = lambda x: x * x
```

Lambda is best for **small, simple functions** that are usually used temporarily.

## Important Points

* Lambda functions are anonymous functions.
* They contain a single expression.
* The result is automatically returned.
* They are commonly used with `map()`, `filter()`, `sorted()`, `min()`, and `max()`.
* They are especially useful for custom sorting in DSA.
* For complex logic, use `def` instead of lambda.

### Quick Memory Trick

```text
map()     → transform
filter()  → select
sorted()  → sort
max()/min() → find
```

**In short:** Lambda = a quick way to create a small function without using `def`.
