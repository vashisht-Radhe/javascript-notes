# 📌 Hoisting in JavaScript

## 🔹 Definition

> **Hoisting** is JavaScript’s behavior of **moving declarations to the top of their scope during the compilation phase**, before code execution.

⚠️ Important:

- **Only declarations are hoisted, not initializations**
- Hoisting happens **before the code runs**

## 🔹 Why Hoisting Exists (Internal Working)

JavaScript executes code in **two phases**:

### 1️⃣ Creation Phase (Compilation)

- Memory is allocated
- Variables and functions are registered

### 2️⃣ Execution Phase

- Code runs line by line
- Values are assigned

Hoisting happens in **Creation Phase**.

## 🔹 Hoisting with `var`

### Example

```js
console.log(a);
var a = 10;
```

### Output

```
undefined
```

### Why?

Internally, JavaScript treats it like this:

```js
var a; // hoisted
console.log(a);
a = 10;
```

### Key Points

- `var` declarations are hoisted
- Initialized with `undefined`
- No error, but value is not available yet

---

## 🔹 Hoisting with `let` and `const`

### Example

```js
console.log(b);
let b = 20;
```

### Output

```
ReferenceError: Cannot access 'b' before initialization
```

### Important Concept: **Temporal Dead Zone (TDZ)**

> **TDZ** is the time between entering scope and variable initialization where `let` and `const` exist but cannot be accessed.

Internally:

```js
// b is hoisted but NOT initialized
console.log(b); // ❌ TDZ
let b = 20;
```

### Key Differences

| Keyword | Hoisted | Initialized | Access before declaration |
| ------- | ------- | ----------- | ------------------------- |
| `var`   | ✅      | `undefined` | ✅                        |
| `let`   | ✅      | ❌          | ❌                        |
| `const` | ✅      | ❌          | ❌                        |

---

## 🔹 Hoisting with Function Declarations

### Example

```js
sayHello();

function sayHello() {
  console.log("Hello!");
}
```

### Output

```
Hello!
```

### Why?

- Function declarations are **fully hoisted**
- Both **function name and body** are hoisted

Internally:

```js
function sayHello() {
  console.log("Hello!");
}
sayHello();
```

✔ Safe to call before definition

---

## 🔹 Hoisting with Function Expressions

### Example (using `var`)

```js
sayHi();

var sayHi = function () {
  console.log("Hi!");
};
```

### Output

```
TypeError: sayHi is not a function
```

### Why?

Internally:

```js
var sayHi; // hoisted
sayHi(); // undefined()
sayHi = function () {
  console.log("Hi!");
};
```

❌ Function body is NOT hoisted

---

### Example (using `let`)

```js
sayHey();

let sayHey = function () {
  console.log("Hey!");
};
```

### Output

```
ReferenceError
```

---

## 🔹 Arrow Functions & Hoisting

Arrow functions behave like **function expressions**.

### Example

```js
hello();

const hello = () => {
  console.log("Hello");
};
```

### Output

```
ReferenceError
```

❌ Arrow functions are **not hoisted**

---

## 🔹 Hoisting and Scope

### Example

```js
function test() {
  console.log(x);
  var x = 5;
}
test();
```

### Output

```
undefined
```

Hoisting is **scope-based**, not global-only.

---

## 🔹 Hoisting in Block Scope

### Example

```js
{
  console.log(a);
  var a = 1;
}
```

✔ Works because `var` ignores block scope.

```js
{
  console.log(b);
  let b = 2;
}
```

❌ Error due to TDZ.

---

## 🔹 Common Interview Traps ⚠️

### Trap 1

```js
var x = 10;

function test() {
  console.log(x);
  var x = 20;
}
test();
```

### Output

```
undefined
```

Why?

```js
function test() {
  var x; // hoisted
  console.log(x);
  x = 20;
}
```

---

### Trap 2

```js
foo();

var foo = function () {
  console.log("Hello");
};
```

❌ Not hoisted as function

---

### Trap 3

```js
let a = 10;
{
  console.log(a);
  let a = 20;
}
```

❌ TDZ error

---

## 🔹 Best Practices (Interview-Friendly)

✅ Always declare variables at the top
✅ Prefer `let` and `const`
✅ Avoid relying on hoisting
✅ Use function declarations for utilities
❌ Avoid `var` in modern JS

---

## 🔹 One-Line Interview Answers

- **Hoisting**: JavaScript moves declarations to the top of scope before execution.
- `var`: Hoisted and initialized as `undefined`.
- `let/const`: Hoisted but in TDZ.
- Function declaration: Fully hoisted.
- Function expression & arrow: Not hoisted.

---

## 🔹 Final Summary Table

| Type                 | Hoisted | Can Call Before |
| -------------------- | ------- | --------------- |
| `var`                | ✅      | ❌              |
| `let`                | ✅      | ❌              |
| `const`              | ✅      | ❌              |
| Function Declaration | ✅      | ✅              |
| Function Expression  | ❌      | ❌              |
| Arrow Function       | ❌      | ❌              |

---

## 🎯 Interview Tip

If interviewer asks:

> **“Is let hoisted?”**

✅ Correct answer:

> “Yes, but it remains in the Temporal Dead Zone until initialized.”
