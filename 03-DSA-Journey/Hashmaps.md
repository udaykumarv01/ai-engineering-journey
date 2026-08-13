First understand the idea

A HashMap stores data in:

KEY → VALUE

Example:

student = {
    "name": "Uday",
    "age": 18,
    "branch": "CSE"
}

Here:

"name"   → "Uday"
"age"    → 18
"branch" → "CSE"

In Python, dict is the main HashMap data structure.

1. Creating a HashMap
mp = {}

mp = {
    "apple": 10,
    "banana": 20,
    "orange": 30
}

You should understand this perfectly before moving ahead.

2. Insert / Update
mp["apple"] = 10
mp["banana"] = 20

If the key already exists:

mp["apple"] = 50

The old value is replaced.

apple → 10

becomes

apple → 50
3. Accessing values
print(mp["apple"])

Output:

50

But this can cause an error if the key doesn't exist.

That's why you'll frequently use:

mp.get("apple")

or:

mp.get("apple", 0)

The second one means:

If "apple" doesn't exist, return 0.

This is very important for DSA.

4. Check whether a key exists
if "apple" in mp:
    print("Found")

This pattern is extremely common in LeetCode.

5. Delete
del mp["apple"]

or:

mp.pop("apple")

Know both, but don't spend much time here.

6. Get all keys and values
mp.keys()
mp.values()
mp.items()

Example:

for key, value in mp.items():
    print(key, value)

Output might be:

banana 20
orange 30
🔥 7. THE MOST IMPORTANT HASHMAP PATTERN: Frequency Counting

This is where HashMaps become extremely useful in DSA.

Suppose:

nums = [1, 2, 2, 3, 1, 2]

We want:

1 → 2
2 → 3
3 → 1
Method 1 — Normal dictionary
freq = {}

for x in nums:
    freq[x] = freq.get(x, 0) + 1

print(freq)

Output:

{1: 2, 2: 3, 3: 1}

8.defaultdict

Python also provides:

from collections import defaultdict

Then:

freq = defaultdict(int)

for x in nums:
    freq[x] += 1

This is cleaner for frequency counting.

You should know it, but don't depend on it until you understand normal dict.

9. HashMap for Lookup

Suppose:

nums = [2, 7, 11, 15]
target = 9

We need two numbers whose sum is 9.

Instead of checking every pair, store previously seen values.

seen = {}

for i, x in enumerate(nums):
    need = target - x

    if need in seen:
        print(seen[need], i)

    seen[x] = i

This is the famous Two Sum pattern.

The important idea isn't memorizing Two Sum.

10.Important HashMap patterns for LeetCode

This is the part I want you to focus on.

Pattern 1 — Frequency
freq[x] = freq.get(x, 0) + 1

Used for:

frequency counting
majority element
anagrams
character counting
Pattern 2 — Seen
seen = set()

if x in seen:
    ...

Used for:

duplicates
unique elements
detecting previously visited values
Pattern 3 — Complement
need = target - x

if need in mp:
    ...

Used for:

Two Sum
pair problems
target-sum problems
Pattern 4 — Value → Index
mp[x] = i

Used when you need to remember:

value → where I saw it
Pattern 5 — Value → Frequency
mp[x] = mp.get(x, 0) + 1

Used when you need:

value → how many times
Pattern 6 — Value → List
mp.setdefault(x, []).append(i)

Used when one key can have multiple associated values.

11.Problems to prove you've learned it on leetcode

Don't solve 30 problems immediately.

Start with these patterns:

Easy

Two Sum
Contains Duplicate
Valid Anagram
Majority Element
First Unique Character in a String
Intersection of Two Arrays

Then move to:

Medium
7. Group Anagrams
8. Top K Frequent Elements
9. Longest Consecutive Sequence
10. Subarray Sum Equals K
