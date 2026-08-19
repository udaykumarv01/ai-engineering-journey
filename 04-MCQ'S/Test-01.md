Topicwise Questions till above topics uploaded in files

PART A — PYTHON FUNDAMENTALS
Q1. What is the output?
x = 10
y = 3


print(x // y)

A) 3.33
B) 3
C) 4
D) 3.0

Q2. Which Python data structure stores key-value pairs?

A) List
B) Tuple
C) Dictionary
D) Set

Q3. Which of the following is mutable?

A) Tuple
B) String
C) Integer
D) List

Q4. What is the output?
x = [1, 2, 3]
y = x


y.append(4)


print(x)

A) [1, 2, 3]
B) [4]
C) [1, 2, 3, 4]
D) Error

Q5. What does range(5) produce?

A) 1,2,3,4,5
B) 0,1,2,3,4
C) 0,1,2,3,4,5
D) 1,2,3,4

Q6. What is the output?
x = [1, 2, 3, 4, 5]


print(x[-1])

A) 1
B) 4
C) 5
D) Error

Q7. Which statement correctly creates a set?

A) s = {1, 2, 2, 3}
B) s = [1, 2, 3]
C) s = (1, 2, 3)
D) s = {"a": 1, "b": 2}

Q8. What is the main advantage of a dictionary?

A) It automatically sorts values
B) It provides fast key-based lookup
C) It only stores integers
D) It cannot be modified

PART B — FUNCTIONS
Q9. What does return do in a function?

A) Prints a value
B) Terminates the entire Python program
C) Sends a value back to the caller
D) Creates a loop

Q10. What does *args allow a function to accept?

A) Multiple keyword arguments only
B) Multiple positional arguments
C) Only integers
D) Only lists

Q11. What does **kwargs represent?

A) Multiple positional arguments
B) Multiple keyword arguments
C) A generator
D) A tuple

Q12. What is the output?
def add(a, b=5):
    return a + b


print(add(10))

A) 10
B) 15
C) 5
D) Error

PART C — COMPREHENSIONS / ITERATORS / GENERATORS
Q13. What does this produce?
[x * 2 for x in range(3)]

A) [0, 1, 2]
B) [2, 4, 6]
C) [0, 2, 4]
D) [1, 2, 3]

Q14. What is the major advantage of a generator?

A) It always executes faster than a list
B) It stores all values permanently
C) It produces values lazily
D) It can only contain strings

Q15. Which keyword is normally used to produce a value from a generator?

A) return
B) yield
C) generate
D) next

Q16. What happens when next() is called on a generator?

A) It restarts the generator
B) It retrieves the next generated value
C) It converts it into a list
D) It deletes the generator

Q17. What is an iterator required to provide?

A) __iter__() and __next__()
B) __start__() and __stop__()
C) begin() and end()
D) next() only

PART D — DECORATORS / ADVANCED PYTHON
Q18. What is the primary purpose of a decorator?

A) Delete a function
B) Modify or extend a function's behavior
C) Convert a function to a class
D) Increase memory usage

Q19. What does @decorator generally represent?

A) Inheritance
B) Function decoration
C) Exception handling
D) A generator

Q20. Why is functools.wraps commonly used inside decorators?

A) To make the function recursive
B) To preserve metadata of the original function
C) To make the function asynchronous
D) To convert the function to a generator

Q21. What does a lambda expression create?

A) Anonymous function
B) Class
C) Generator only
D) Module

Q22. Which is a valid lambda?

A) lambda x: x * 2
B) lambda: x -> x * 2
C) function x: x * 2
D) def lambda(x): x * 2

PART E — OOP
Q23. What is encapsulation?

A) Creating multiple loops
B) Bundling data and methods together and controlling access
C) Sorting objects
D) Converting objects into lists

Q24. What does inheritance allow?

A) A class to acquire behavior from another class
B) A function to return multiple values
C) A list to become immutable
D) A dictionary to become sorted

Q25. What is polymorphism?

A) One interface/name behaving differently depending on the object/context
B) Creating only one object
C) Hiding every variable
D) Preventing inheritance

Q26. What is the purpose of __init__()?

A) Destroy an object
B) Initialize an object
C) Import a module
D) Create a generator

Q27. In an instance method, what does self normally refer to?

A) Parent class
B) Current object/instance
C) Python interpreter
D) Module

Q28. Which concept allows method names to have different implementations in different classes?

A) Encapsulation
B) Abstraction
C) Polymorphism
D) Compilation

PART F — DSA: HASHING / HASHMAP
Q29. In Python, which data structure is primarily used as a HashMap?

A) list
B) tuple
C) dict
D) str

Q30. What is the average-case time complexity of dictionary lookup?

A) O(n²)
B) O(n)
C) O(log n)
D) O(1)

Q31. What does this pattern accomplish?
freq[x] = freq.get(x, 0) + 1

A) Sorting
B) Frequency counting
C) Binary search
D) Reversing

Q32. Which structure is usually best when you only need to know whether an element has appeared before?

A) Set
B) Tuple
C) String
D) Float

Q33. What is a hash collision?

A) Two keys producing the same hash-table location/bucket
B) Two lists being equal
C) Two loops running together
D) A dictionary becoming empty

Q34. Which problem is a classic HashMap application?

A) Two Sum
B) Binary Tree Traversal
C) Merge Sort only
D) Linked List Reversal only

PART G — TWO POINTERS
Q35. What is the main idea behind the Two Pointer technique?

A) Always use two arrays
B) Maintain two positions and move them intelligently
C) Always use recursion
D) Always use a HashMap

Q36. For a sorted array, if:
nums[left] + nums[right] < target

in a typical two-pointer pair-sum problem, what should you do?

A) left -= 1
B) right += 1
C) left += 1
D) Stop immediately

Q37. Why does Two Sum with two pointers work naturally on a sorted array?

A) Sorting allows us to determine which side can be eliminated
B) Sorting makes every number unique
C) Sorting creates a HashMap
D) Sorting makes lookup O(1)

Q38. What is the typical complexity of finding a pair sum in a sorted array using two pointers?

A) O(n²)
B) O(n log n) after sorting, or O(n) if already sorted
C) O(2ⁿ)
D) O(n³)

Q39. Which pattern is commonly used to reverse an array in-place?

A) HashMap
B) Left and right pointers
C) Binary tree
D) Queue only

Q40. In a slow-fast pointer technique, which statement is usually true?

A) Both pointers always move at the same speed
B) Fast pointer progresses faster than slow pointer
C) Slow pointer never moves
D) Fast pointer always moves backward

PART H — SLIDING WINDOW
Q41. Sliding Window is primarily useful for problems involving:

A) Non-contiguous random elements only
B) Continuous ranges such as subarrays/substrings
C) Classes and objects
D) Graph edges only

Q42. What does this expression represent?
right - left + 1

A) Number of windows
B) Current window size
C) Number of duplicates
D) Array capacity

Q43. In a fixed-size sliding window of size k, when:
right - left + 1 == k

what generally happens?

A) We process the window and then move it
B) We stop the program permanently
C) We sort the entire array
D) We reset right to zero

Q44. Why is Sliding Window often O(n) even when it contains a for loop and a while loop?

A) The while loop always runs once
B) left and right generally each move through the data at most O(n) times
C) Python ignores the while loop
D) Nested loops are always O(n)

Q45. In a variable-size window, what is the usual purpose of moving left?

A) Expand the window
B) Shrink the window when the condition is invalid
C) Sort the window
D) Delete the entire array

Q46. Which combination is extremely common in substring problems?

A) Sliding Window + HashMap/Set
B) Binary Tree + Stack only
C) Recursion + Heap only
D) Sorting + Matrix only

PART I — BINARY SEARCH
Q47. What is the primary requirement for ordinary Binary Search?

A) Array must always contain duplicates
B) Search space must be sorted or have an appropriate monotonic property
C) Array must contain strings
D) Array must have exactly 10 elements

Q48. What is the time complexity of Binary Search?

A) O(n²)
B) O(n)
C) O(log n)
D) O(2ⁿ)

Q49. Suppose:
nums[mid] < target

What should happen in standard Binary Search?

A) right = mid - 1
B) left = mid + 1
C) left = mid - 1
D) right = mid + 1

Q50. What is the key idea behind Binary Search on Answer?

A) Search for an answer in a monotonic/ordered range of possible answers
B) Search only for array indices
C) Always sort the answer
D) Use two HashMaps simultaneously

🏆 BONUS — INTERVIEW THINKING

These are not just syntax questions. They test whether you've actually understood the patterns.

Q51. You are given an unsorted array and need to find whether two numbers sum to a target in O(n) average time. Which approach is most natural?

A) Nested loops
B) HashMap/Set
C) Binary Search without sorting
D) Recursion only

Q52. You are given a sorted array and need to find whether two numbers sum to a target. Which approach can achieve O(n)?

A) Two Pointers
B) Nested loops
C) DFS
D) Dynamic Programming

Q53. You need the longest substring without repeating characters. Which combination is most appropriate?

A) Binary Search
B) Sliding Window + Set/HashMap
C) Two nested loops only
D) Heap

Q54. You need the smallest contiguous subarray whose sum is at least target. Which pattern should immediately come to mind?

A) Variable Sliding Window
B) OOP
C) Binary Tree
D) Hashing only

Q55. You need to find a target in a sorted array in O(log n). Which technique?

A) Sliding Window
B) HashMap
C) Binary Search
D) Two Pointers only

🧠 FINAL INTERVIEW SCENARIO
Q56.

You are given:

nums = [1, 2, 3, 4, 5, 6, 7]

You need to find two numbers whose sum is 8.

Which is the best pattern if the array is already sorted?

A) HashMap only
B) Two Pointers
C) Sliding Window
D) DFS

Q57.

You are given:

nums = [4, 1, 7, 2, 9]

The array is unsorted, and you need two numbers whose sum is 10 in average O(n).

A) Binary Search
B) Two Pointers directly
C) HashMap
D) Sliding Window

Q58.

You need the maximum sum of exactly k consecutive elements.

A) Fixed Sliding Window
B) Binary Search
C) HashMap only
D) Two Pointers from both ends

Q59.

You need to find the first occurrence of a target in:

[1, 2, 2, 2, 3, 4]

Which concept should you use?

A) Standard linear search only
B) Modified Binary Search
C) Sliding Window
D) HashMap only

Q60.

Which statement best describes your DSA learning so far?

A) Memorizing Python syntax
B) Learning problem-solving patterns and recognizing when to use them
C) Only learning C pointers
D) Only learning LeetCode answers

Solutions:
1. B
2. C
3. D
4. C
5. B
6. C
7. A
8. B
9. C
10. B
11. B
12. B
13. C
14. C
15. B
16. B
17. A
18. B
19. B
20. B
21. A
22. A
23. B
24. A
25. A
26. B
27. B
28. C
29. C
30. D
31. B
32. A
33. A
34. A
35. B
36. C
37. A
38. B
39. B
40. B
41. B
42. B
43. A
44. B
45. B
46. A
47. B
48. C
49. B
50. A
51. B
52. A
53. B
54. A
55. C
56. B
57. C
58. A
59. B
60. B
