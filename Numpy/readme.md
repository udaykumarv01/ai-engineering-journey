# NumPy — Complete Course Notes

My notes and practice code from the **Complete NumPy – Basic to Advanced** series on the [Decode AiML](https://www.youtube.com/@decodeAiML) YouTube channel. This is part of my AI/ML journey. Every section below maps to one lecture of the course, with the code I practiced and the things that tripped me up.

> 🎬 **Course page (all 10 lectures):** [decodeaiml.com – Complete NumPy](https://decodeaiml.com/04.%20Complete%20NumPy%20-%20Basic%20to%20Advanced/)
> 📺 **Channel:** [@decodeAiML](https://www.youtube.com/@decodeAiML)
> 📒 **Official notes and notebooks:** [Decode-AiML on GitHub](https://github.com/Decode-AI-By-Sanjeev/Decode-AiML/tree/main/04.%20Complete%20NumPy%20-%20Basic%20to%20Advanced)

📓 Notebooks in this repo: `01_numpy_basics.ipynb` (data types) and `numpy_basics.ipynb` (statistics, correlation, matrix operations).

---

## Course Map

| # | Lecture | Video |
|---|---------|-------|
| 4.1 | Introduction to NumPy: why it is fast, NumPy vs Pandas vs Lists | [Watch](https://youtu.be/l_ZqAOkUadY) |
| 4.2 | NumPy datatypes: homogeneous and heterogeneous arrays | [Watch](https://youtu.be/ibRSLcuRjTU) |
| 4.3 | Introduction to NumPy arrays and creating them | [Watch](https://youtu.be/6vUfhWFklL4) |
| 4.4 | Basic maths for NumPy: diagonal, identity and triangular matrices, random, log/linear space | [Watch](https://youtu.be/2oxfO9Ji0ug) |
| 4.5 | Creating arrays with built-in methods: arange, linspace, logspace, diag, eye, rand, randn | [Watch](https://youtu.be/2BX2X3bYeg8) |
| 4.6 | Dimension, shape, axis, vectorization and broadcasting | [Watch](https://youtu.be/7iJ7OeRLazE) |
| 4.7 | Indexing, slicing and subsetting | [Watch](https://youtu.be/HtljDoF778k) |
| 4.8 | Maths on NumPy arrays | [Watch](https://youtu.be/UAsuR18DuK0) |
| 4.9 | Linear algebra and statistics using NumPy | [Watch](https://youtu.be/w6azl3z_mig) |
| 4.10 | Built-in functions: ravel, moveaxis, squeeze, concatenate, stack, split, tile, repeat, append, unique | [Watch](https://youtu.be/rYRXSIoOQxo) |

## About the Playlist

**Complete NumPy – Basic to Advanced** is a 10-lecture playlist on NumPy tools for data science and AI/ML. Topics: introduction and why NumPy is fast, datatypes, creating arrays, basic maths, built-in creators, dimension/shape/axis/vectorization/broadcasting, indexing and slicing, maths on arrays, linear algebra and statistics, and built-in manipulation functions.

## Topics Learned

- Why NumPy is fast, and how it compares with lists and Pandas
- Creating 1D and multidimensional arrays; `.size`, `.shape`, `.ndim`
- Data types (`int16`, `int32`, `float32`, Unicode strings), type conversion, structured and object arrays
- `np.array()` vs `np.asarray()`, upcasting, saving and loading (`.txt`, `.npy`, `.npz`)
- `arange`, `linspace`, `logspace`, `diag`, `eye`, `tri`, `tril`, `triu`, `rand`, `randn`
- Axis, vectorization and broadcasting
- Indexing, slicing, boolean subsetting, views vs copies, sorting
- Element-wise maths and built-in math functions
- Statistics: mean, median, mode, variance, standard deviation, correlation, covariance, percentile
- Linear algebra: sum, product, trace, transpose, dot, inner, outer
- Array manipulation: `ravel`, `moveaxis`, `squeeze`, `concatenate`, `stack`, `split`, `tile`, `repeat`, `append`, `unique`

---

## 1. Introduction: Why NumPy?

```python
!pip install numpy
import numpy as np
```

`np` is the standard alias. NumPy is fast because:

- Arrays store **one data type in a contiguous block of memory**, unlike a Python list of separate objects.
- The heavy loops run in compiled **C**, not in the Python interpreter.
- **Vectorized** operations apply to the whole array at once (section 6).

| | Python list | NumPy array | Pandas |
|---|---|---|---|
| Data types | Mixed | One dtype (usually) | Mixed, per column |
| Speed for numeric work | Slow | Fast | Built on NumPy |
| Best for | General storage | Numeric and matrix computation | Labelled, tabular data |

NumPy is the base layer of almost every ML library, so it matters.

## 2. Creating Arrays, Size and Shape

```python
a1D = np.array([1, 2, 3, 4])
print(a1D)        # [1 2 3 4]
a1D.size          # 4

arr = np.array([
    [[1, 2, 7], [4, 7, 5]],
    [[7, 7, 8], [1, 2, 3]]
])
arr.size          # 12
arr.shape         # (2, 2, 3)
arr.ndim          # 3
```

`.size` is the total number of elements. The shape `(2, 2, 3)` means 2 blocks, each with 2 rows, each row with 3 elements, so 2 × 2 × 3 = 12.

## 3. Data Types

Every array has a `dtype`:

```python
np.array([1, 2, 3], dtype=np.int32)             # array([1, 2, 3], dtype=int32)
np.array([1.1, 2.2, 3.3], dtype=np.float32)     # array([1.1, 2.2, 3.3], dtype=float32)
```

### Type conversion

```python
np.array([1.1, 2.2, 3.3], dtype=np.int32)       # [1 2 3]  (truncated, not rounded)
np.array([True, False, True], dtype=np.int32)   # [1 0 1]
np.array([1, "4", 3], dtype=np.int16)           # [1 4 3]
```

- float → int truncates the fraction (3.3 → 3).
- bool → int: `True` → 1, `False` → 0.
- `"4"` converts only because I asked for `dtype=np.int16` explicitly.
- Without a `dtype`, mixed input is **upcast** to one common type: `np.array([1, "4", 3])` becomes a string array, and `np.array([1, 2.5, True])` becomes `float64`.

### Unicode string arrays

```python
A = np.array(["Apple", "Banana"])                # <U6
B = np.array(["Apple", "Banana"], dtype="U10")   # <U10
C = np.array(["Apple", "Banana"], dtype="U5")    # <U5 -> ['Apple' 'Banan']
```

`<U` means Unicode string and the number is the maximum number of characters, so longer strings get cut.

### Structured arrays (mixed types, named fields)

```python
records = [("Uday", "18", "88"), ("Yogesh", "19", "98")]

data = np.array(
    records,
    dtype=[("name", "U15"), ("age", np.int32), ("marks", np.int32)]
)
print(data)            # [('Uday', 18, 88) ('Yogesh', 19, 98)]
print(data[0])         # ('Uday', 18, 88)
print(data["name"])    # ['Uday' 'Yogesh']
```

### Object arrays

```python
het = np.array([5, 4.5, True, "a"])                  # everything becomes a string
het = np.array([5, 4.5, True, "a"], dtype=object)    # [5 4.5 True 'a']
het[0], type(het[0])                                 # (5, <class 'int'>)
```

`dtype=object` keeps each value as its own Python object, with no forced conversion.

### Errors I hit

```python
np.array([1, "a", 3], dtype=np.int16)
# ValueError: invalid literal for int() with base 10: 'a'
```
`"a"` cannot become an integer.

```python
np.array(["a", c, "b"], dtype=np.str_)
# NameError: name 'c' is not defined
```
I used a variable before defining it (`c` should have been `"c"`).

`help(np.array)` shows every parameter, so there is no need to memorize them.

## 4. `array` vs `asarray`, Saving and Loading

```python
x = np.array([1, 2, 3])
y = np.array(x)       # always makes a copy
z = np.asarray(x)     # reuses x if it is already an ndarray of that dtype
```

**Text files** are human-readable but slow and large:

```python
np.savetxt("data.txt", x)
np.loadtxt("data.txt")
```

**Binary files** are fast, compact and keep the dtype:

```python
np.save("arr.npy", x)                 # one array
np.load("arr.npy")

np.savez("arrays.npz", a=x, b=y)      # several arrays in one file
npz = np.load("arrays.npz")
npz["a"]
```

## 5. Built-in Array Creators

```python
np.arange(0, 10, 2)      # [0 2 4 6 8]         like range(), but returns an array
np.linspace(0, 1, 5)     # [0.  0.25 0.5  0.75 1. ]   5 evenly spaced points, end included
np.logspace(0, 3, 4)     # [1. 10. 100. 1000.]  powers of 10 from 10^0 to 10^3
```

**Vector, matrix, tensor:** 1D, 2D and 3D+ arrays. A matrix is *square* when rows = columns, otherwise *rectangular*.

```python
m = np.arange(1, 10).reshape(3, 3)

np.diag(m)               # [1 5 9]          main diagonal
np.diag(m, k=1)          # [2 6]            one above the main diagonal
np.diag([1, 2, 3])       # 3x3 matrix with these values on the diagonal

np.eye(3)                # identity matrix
np.tri(3)                # lower-triangular matrix of ones
np.tril(m)               # keep lower triangle, zero the rest
np.triu(m)               # keep upper triangle, zero the rest
```

**Random numbers:**

```python
np.random.rand(3)        # uniform distribution on [0, 1)
np.random.randn(3)       # normal distribution (mean 0, std 1)
np.random.randint(1, 10, 9).reshape(3, 3)   # integers; the upper bound is exclusive
np.random.seed(42)       # makes results reproducible
```

## 6. Dimension, Shape, Axis, Vectorization and Broadcasting

- **Axis 0** runs down the rows (one result per column); **axis 1** runs across the columns (one result per row).
- **Vectorization:** operating on a whole array without writing a Python loop, which is much faster:

```python
a = np.arange(1_000_000)

# slow: Python loop
result = [i * 2 for i in a]

# fast: vectorized
result = a * 2
```

- **Broadcasting:** NumPy stretches smaller arrays to match larger ones. Shapes are compared from the right, and two dimensions are compatible if they are equal or one of them is 1.

```python
m + np.array([10, 20, 30])
# [[11 22 33]
#  [14 25 36]
#  [17 28 39]]

np.arange(3).reshape(3, 1) + np.arange(3)    # (3,1) + (3,) -> (3,3)
# [[0 1 2]
#  [1 2 3]
#  [2 3 4]]
```

## 7. Indexing, Slicing and Subsetting

```python
a = np.arange(10)
a[2]            # 2
a[2:5]          # [2 3 4]
a[::-1]         # reversed
m[1, 2]         # row 1, column 2 -> 6
m[:, 0]         # first column
m[0:2, 1:3]     # sub-matrix

a[a > 5]        # boolean subsetting -> [6 7 8 9]
```

### View vs copy

```python
s = a[2:5]
s[0] = 99        # also changes a, because a slice is a VIEW
c = a[2:5].copy()
c[0] = 0         # a is unchanged, because .copy() is independent
```

### Sorting and max

```python
np.sort(a)       # returns a sorted copy
a.max(), a.argmax()
```

## 8. Maths on Arrays

```python
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

x + y, x - y, x * y, x / y     # element-wise
x ** 2
x + 10                          # broadcasting a scalar

np.add(x, y), np.subtract(x, y), np.multiply(x, y), np.divide(x, y)
np.exp(x), np.sqrt(x), np.log(x)
```

`*` is **element-wise**, not matrix multiplication (use `np.dot` or `@` for that).

## 9. Statistics and Linear Algebra

📓 Full code in `numpy_basics.ipynb`.

```python
from numpy.random import randint

mat1 = randint(1, 10, 9).reshape(3, 3)

np.sum(mat1)                 # sum of all elements
np.prod(mat1)                # product of all elements
np.sum(mat1, axis=0)         # column-wise sum
np.sum(mat1, axis=1)         # row-wise sum
np.mean(mat1)                # overall mean
np.mean(mat1[0])             # mean of row 0
```

### Spread and middle value

```python
mat = randint(1, 100, 9).reshape(3, 3)
np.std(mat)                  # standard deviation
np.var(mat)                  # variance
np.median(mat)               # works without sorting first

np.percentile(mat, 50)       # same as the median
np.quantile(mat, 0.25)       # first quartile
```

NumPy has **no `np.mode`**. To find the mode, use `np.unique` with counts:

```python
values, counts = np.unique(x, return_counts=True)
values[counts.argmax()]
```

### Correlation and covariance

```python
A = randint(1, 50, 20)
B = 2 * A + 10 * np.random.randn(20)     # B depends on A, plus noise

np.corrcoef(A, B)    # about 0.97 -> strong positive correlation
np.corrcoef(A, A)    # all 1s: a variable correlates perfectly with itself
np.cov(A, B)         # covariance matrix
```

```python
import matplotlib.pyplot as plt
plt.scatter(A, B)
plt.title("Scatter plot of A vs. B")
plt.show()
```

Two unrelated random arrays give a correlation near 0 (I got about -0.25 on 20 random points), while a linear relationship gives a value close to 1.

### Linear algebra

```python
A = randint(1, 10, 9).reshape(3, 3)
B = randint(1, 10, 9).reshape(3, 3)

np.dot(A, B)                 # matrix product (same as A @ B)
np.transpose(A)              # same as A.T
np.trace(A)                  # sum of the main diagonal
np.diag(A)

v = np.array([1, 2, 3]); w = np.array([4, 5, 6])
np.dot(v, w)                 # 32  -> one number for 1D vectors
np.inner(v, w)               # 32
np.outer(v, [4, 5])          # 3x2 matrix of all pairwise products
```

Transposing a 3×2 matrix gives a 2×3 matrix.

## 10. Array Manipulation

```python
a = np.arange(6).reshape(2, 3)
p = np.array([1, 2, 3]); q = np.array([4, 5, 6])

np.ravel(a)                          # flatten to 1D -> [0 1 2 3 4 5]
np.moveaxis(np.zeros((2, 3, 4)), 0, -1).shape   # (3, 4, 2)
np.squeeze(np.zeros((1, 3, 1))).shape           # (3,)  removes size-1 axes

np.concatenate([p, q])               # [1 2 3 4 5 6]
np.stack([p, q])                     # [[1 2 3] [4 5 6]]   new axis
np.stack([p, q], axis=1)             # [[1 4] [2 5] [3 6]]
np.split(np.arange(6), 3)            # [array([0, 1]), array([2, 3]), array([4, 5])]

np.tile(p, 2)                        # [1 2 3 1 2 3]   repeats the whole array
np.repeat(p, 2)                      # [1 1 2 2 3 3]   repeats each element
np.append(p, [7, 8])                 # [1 2 3 7 8]
np.unique(np.array([1, 2, 2, 3]))    # [1 2 3]
```

---

## Key Takeaways

- NumPy is fast because of contiguous, single-type memory, C loops and vectorization.
- `.size` = total elements, `.shape` = size along each dimension, `.ndim` = number of dimensions.
- `dtype` controls storage. Float → int truncates, and `True`/`False` → 1/0.
- Mixed input is upcast to one type, unless you use structured arrays or `dtype=object`.
- `np.array()` copies, `np.asarray()` avoids a copy when it can. Use `.npy`/`.npz` for fast binary storage.
- `axis=0` works down the rows (per column) and `axis=1` works across columns (per row).
- Broadcasting compares shapes from the right: dimensions must match or be 1.
- Slices are **views**; use `.copy()` when you need independence.
- `*` is element-wise. Use `np.dot` or `@` for matrix multiplication.
- Correlation near 1 or -1 means a strong linear relationship; near 0 means little or none.
- `help()` is the quickest way to read documentation.

## Credits

Course by **Decode AiML**: [YouTube channel](https://www.youtube.com/@decodeAiML) · [Course page](https://decodeaiml.com/04.%20Complete%20NumPy%20-%20Basic%20to%20Advanced/) · [GitHub](https://github.com/Decode-AI-By-Sanjeev/Decode-AiML).
These notes and code are my own practice.
