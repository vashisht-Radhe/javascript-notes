# Call Stack in JavaScript

## What is the Call Stack?

The call stack is a **data structure** that keeps track of **which function is currently running** in JavaScript.

It works on:

> LIFO - Last In, First Out

## Why do we need the Call Stack?

JavaScript needs a way to:

- know where it is in the code
- know which function to return to
- manage function execution order

The call stack handles all of this.

## Simple Example

```js
function greet() {
  console.log("Hello");
}

greet();
```

**How it works**

1. `greet()` is pushed to the stack
2. `console.log()` runs
3. Stacks becomes empty

### Output

```bash
Hello
```

## Nested Function Example

```js
function first() {
  second();
  console.log("First");
}

function second() {
  third();
  console.log("Second");
}

function third() {
  console.log("Third");
}

first();
```

**Call Stack Order**

```bash
first()
second()
third()
```

**Output**

```bash
Third
Second
First
```

**Explanation**

- `third()` finishes first
- then `second()`
- then `first()`

Last in → First out.

**Call Stack + Error Example**

```js
function one() {
  two();
}

function two() {
  three();
}

function three() {
  throw new Error("Something went wrong");
}

one();
```

**What happens?**

- Error occurs
- Call stack is printed
- Shows function execution path

This is how stack traces work.

**Important Rules**

- JavaScript has only ONE call stack
- Only synchronous code runs here
- If stack is blocked → app freezes

**Summary**

- Call stack tracks function execution
- Uses LIFO
- Executes synchronous code
- Too much recursion can crash it
