Async / Await in Python

1. What is "async"?

"async" is used to define an asynchronous function (also called a coroutine).

async def hello():
    print("Hello")

Calling "hello()" does not execute it immediately. It creates a coroutine object.

To run it:

import asyncio

async def hello():
    print("Hello")

asyncio.run(hello())

---

2. What is "await"?

"await" is used to wait for an asynchronous operation to complete.

While waiting, the event loop can run other asynchronous tasks.

Example:

import asyncio

async def hello():
    await asyncio.sleep(2)
    print("Hello")

asyncio.run(hello())

Here, "await" pauses the coroutine for 2 seconds without blocking the entire program.

---

3. Why use Async Programming?

Imagine we need to call 3 APIs:

API 1 → waits 2 seconds
API 2 → waits 2 seconds
API 3 → waits 2 seconds

Normal / Synchronous approach

API 1 → 2 sec
API 2 → 2 sec
API 3 → 2 sec

Total ≈ 6 seconds

Each operation waits for the previous one to finish.

Asynchronous approach

The tasks can make progress while other tasks are waiting.

Task 1 ──┐
Task 2 ──┼── run concurrently
Task 3 ──┘

This is especially useful for I/O-bound operations such as:

- API requests
- Network communication
- Database operations
- File I/O

---

4. Coroutine

A function defined using "async def" is a coroutine function.

async def task():
    print("Running...")

A coroutine can be scheduled and executed by Python's event loop.

import asyncio

async def task():
    print("Running...")

asyncio.run(task())

---

5. "asyncio"

"asyncio" is Python's library for writing asynchronous programs.

Common functions:

import asyncio

asyncio.run()
asyncio.sleep()
asyncio.gather()

---

6. Running Multiple Tasks

Instead of waiting for tasks one by one, we can run multiple coroutines concurrently.

import asyncio

async def task(name):
    print(f"{name} started")
    await asyncio.sleep(2)
    print(f"{name} finished")

async def main():
    await asyncio.gather(
        task("Task 1"),
        task("Task 2"),
        task("Task 3")
    )

asyncio.run(main())

The tasks can make progress during each other's "await" periods.

---

7. Synchronous vs Asynchronous

Synchronous| Asynchronous
Runs operations sequentially| Can run multiple tasks concurrently
Blocking waits are common| "await" allows other tasks to run
Simple to understand| Useful for I/O-heavy programs
Can be slower for many I/O operations| Can improve responsiveness

Key idea

«Async programming is mainly about not wasting time while waiting for I/O operations.»

---

Quick Summary

async def
    ↓
Creates a coroutine function
    ↓
await
    ↓
Wait for an async operation
    ↓
Event Loop
    ↓
Can run other tasks while waiting
    ↓
Concurrency + better I/O performance

Remember

- "async" → defines a coroutine function
- "await" → waits for an asynchronous operation
- "asyncio" → Python's async programming library
- Coroutine → asynchronous function/object
- Event loop → manages and schedules async tasks
- Best suited for I/O-bound work
