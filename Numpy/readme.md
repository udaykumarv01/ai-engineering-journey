# NumPy — Day 1

My first hands-on NumPy session as part of my AI/ML journey. This is a record of what I actually practiced today — arrays, `.size` / `.shape`, and a lot of `dtype` experiments (including the errors I hit). Basics only; there is much more to learn.

📓 Notebook: [`01_numpy_basics.ipynb`](01_numpy_basics.ipynb)

## Topics Learned

- Installing and importing NumPy
- Creating 1D and multidimensional arrays with `np.array()`
- `.size` and `.shape`
- Data types: `np.int16`, `np.int32`, `np.float32`, `np.str_`
- Type conversion (float → int, bool → int, string number → int)
- Unicode string dtypes (`<U6`, `<U10`, `<U5`)
- Structured arrays and `dtype=object`
- Reading documentation with `help()`
- Debugging a `ValueError` and a `NameError`

## 1. Installing and Importing NumPy

```python
!pip install numpy
import numpy as np
```

`pip` installs Python packages (NumPy was already in my Miniconda environment). `np` is the standard alias for NumPy.

## 2. Creating NumPy Arrays

```python
a1D = np.array([1, 2, 3, 4])
print(a1D)        # [1 2 3 4]
```

`np.array()` builds an array from a Python sequence. A flat list gives a one-dimensional array.

## 3. Array Size and Shape

```python
a1D.size          # 4

arr = np.array([
    [[1, 2, 7], [4, 7, 5]],
    [[7, 7, 8], [1, 2, 3]]
])
arr.size          # 12
arr.shape         # (2, 2, 3)
```

`.size` is the total number of elements. The shape `(2, 2, 3)` means **2** blocks, each with **2** rows, each row with **3** elements → 2 × 2 × 3 = **12** elements.

## 4. NumPy Data Types

Every array has a `dtype` that determines the type of data it stores. NumPy provides fixed-size types:

```python
np.array([1, 2, 3], dtype=np.int32)             # array([1, 2, 3], dtype=int32)
np.array([1.1, 2.2, 3.3], dtype=np.float32)     # array([1.1, 2.2, 3.3], dtype=float32)
```

- `np.int32` — 32-bit signed integer (`np.int16` is the 16-bit version)
- `np.float32` — 32-bit floating-point number
- `np.str_` / `U` types — Unicode strings (section 6)
- `dtype=object` — Python objects (section 8)

## 5. Type Conversion

```python
np.array([1.1, 2.2, 3.3], dtype=np.int32)       # array([1, 2, 3], dtype=int32)
np.array([True, False, True], dtype=np.int32)   # array([1, 0, 1], dtype=int32)
np.array([1, "4", 3], dtype=np.int16)           # [1 4 3] int16
```

- **float → int:** the fractional part is truncated, not rounded (`3.3` → `3`).
- **bool → int:** `True` → `1`, `False` → `0`.
- **string number → int:** `"4"` is a valid number, so it converts when `dtype=np.int16` is given explicitly.

Without an explicit dtype, mixing values makes NumPy pick one common dtype: `np.array([1, "4", 3])` becomes a string array.

## 6. Unicode/String Arrays

```python
A = np.array(["Apple", "Banana"])                # <U6
B = np.array(["Apple", "Banana"], dtype="U10")   # <U10
C = np.array(["Apple", "Banana"], dtype="U5")    # <U5  -> ['Apple' 'Banan']
```

`<U` means Unicode string; the number is the maximum characters per string.

- `A`: NumPy inferred `<U6` because `"Banana"` has 6 characters.
- `B`: `U10` allows up to 10 characters.
- `C`: `U5` allows only 5, so `"Banana"` is cut to `"Banan"`.

`np.str_` is NumPy's Unicode string scalar type, so `dtype=np.str_` explicitly requests string data.

## 7. Structured Arrays

```python
records = [("Uday", "18", "88"), ("Yogesh", "19", "98")]

np.array(records)      # everything stays a string

data = np.array(
    records,
    dtype=[("name", "U15"), ("age", np.int32), ("marks", np.int32)]
)
print(data)            # [('Uday', 18, 88) ('Yogesh', 19, 98)]
print(data[0])         # ('Uday', 18, 88)
print(data["name"])    # ['Uday' 'Yogesh']
```

A structured array lets different fields have different dtypes: `name` is a Unicode string (max 15 chars), `age` and `marks` are `int32`. `data[0]` gets the first record; `data["name"]` gets the name field for every record.

## 8. Object Arrays

```python
het = np.array([5, 4.5, True, "a"])                  # all converted to strings
het = np.array([5, 4.5, True, "a"], dtype=object)    # [5 4.5 True 'a'] object
het[0], type(het[0])                                 # 5 <class 'int'>
```

With `dtype=object`, the array holds Python objects of different types (`int`, `float`, `bool`, `str`) without forcing them into one dtype.

## 9. Documentation and Debugging

`help(np.array)` shows a function's parameters and options, so there is no need to memorize them.

**Errors I hit (and what they taught me):**

```python
np.array([1, "a", 3], dtype=np.int16)
# ValueError: invalid literal for int() with base 10: 'a'
```
I asked for `int16`; `1` and `3` convert, but `"a"` can't become an integer, so NumPy raises `ValueError`.

```python
np.array(["a", c, "b"], dtype=np.str_)
# NameError: name 'c' is not defined
```
`c` was never defined, so Python raised `NameError` — define a variable before using it.

## Key Takeaways

- `np.array()` creates arrays from Python sequences; nesting adds dimensions.
- `.size` = total elements; `.shape` = size along each dimension.
- `dtype` controls how data is stored: `np.int16`, `np.int32`, `np.float32`, `np.str_`.
- Float → int truncates; `True`/`False` → `1`/`0`.
- In `<U5`-style dtypes, the number is the max string length, and longer strings get cut.
- Arrays normally have one dtype; structured arrays (named fields) and `dtype=object` allow mixed types.
- `help()` is a quick way to read documentation.
