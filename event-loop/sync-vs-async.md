# Synchronous vs Asynchronous JavaScript

## What does synchronous mean?

Synchronous code is executed **line by line**, one after another.
JavaScript **waits** for one line to finish before moving to the next.

In simple words:

> “Do this first, finish it completely, then go to the next task.”

## Example: Synchronous Code

```js
console.log("First");
console.log("Second");
console.log("Third");
```

## Output

```bash
First;
Second;
Third;
```

Each line waits for the previous one to finish.
No skipping, no delay.

# What does asynchronous mean?

Asynchronous code allows JavaScript to **start a task and move on**, without waiting for that task to finish.

This is needed for:

- timers
- API calls
- file reading
- database operations

## Example: Asynchronous Code

```js
console.log("Start");

setTimeout(() => {
  console.log("Inside timeout");
}, 1000);

console.log("End");
```

- `setTimeout` is asynchronous
- JavaScript does NOT wait 1 second
- It moves on and prints End
- Timeout callback runs later

## Why javaScript needs async behavior

JavaScript is **single-threaded**.

If everything was synchronous:

- the browser would freeze
- UI would stop responding
- user experience would be bad

Async code keeps apps fast and responsive.

### Key Diffferences

| Synchronous           | Asynchronous           |
| --------------------- | ---------------------- |
| Blocking              | Non-blocking           |
| Executes line by line | Executes in background |
| Simple but slow       | Complex but efficient  |

### Important Note

Asynchronous does NOT mean multi-threaded.
JavaScript still runs on **one main thread**.

Async behavior is handled by:

- browser APIs
- Node.js APIs
- event loop

**Summary**

- Sync = wait and execute
- Async = start and move on
- JavaScript uses async to stay fast
