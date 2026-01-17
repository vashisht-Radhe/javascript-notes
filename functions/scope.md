# JavaScript Scope

**Scope** determines **where variables can be accessed** in your code.  
In simple words, scope answers the question:

> ❓ _Where can I use this variable?_

## 1. Types of Scope in JavaScript

JavaScript has **three main types of scope**:

1. Global Scope
2. Function Scope
3. Block Scope

## 1.1. Global Scope

### Definition

Variables declared **outside any function or block** are in the global scope.

### Example

```js
let globalVar = "I am global";

function show() {
  console.log(globalVar);
}

show();
console.log(globalVar);
```

### Output

```txt
I am global
I am global
```

### Notes

- Accessible everywhere
- ❌ Overusing global variables is bad practice

## 1.2. Function Scope

### Definition

Variables declared **inside a function** are accessible **only within that function**.

### Example

```js
function test() {
  let message = "Hello";
  console.log(message);
}

test();
```

```js
console.log(message); // Error
```

### Output

```txt
Hello
ReferenceError: message is not defined
```

## 1.3. Block Scope (`let` & `const`)

### Definition

Variables declared with `let` and `const` inside `{}` are **block-scoped**.

### Example

```js
if (true) {
  let x = 10;
  const y = 20;
  console.log(x, y);
}

console.log(x); // Error
```

### Output

```txt
10 20
ReferenceError: x is not defined
```

## 2. `var` and Scope (Important ⚠️)

### Key Point

`var` is **NOT block-scoped**, it is **function-scoped**.

### Example

```js
if (true) {
  var a = 5;
}

console.log(a);
```

### Output

```txt
5
```

❌ This behavior causes bugs
✅ Prefer `let` and `const`

---

## 3. Lexical Scope

### Definition

Scope is determined by **where variables are written in the code**, not where functions are called.

### Example

```js
let name = "Global";

function greet() {
  console.log(name);
}

function callGreet() {
  let name = "Local";
  greet();
}

callGreet();
```

### Output

```txt
Global
```

👉 `greet()` uses the scope where it was **defined**, not called.

## 4. Temporal Dead Zone (TDZ)

### Definition

Variables declared with `let` and `const` exist in a **temporal dead zone** from the start of the block until declaration.

### Example

```js
console.log(x);
let x = 10;
```

### Output

```txt
ReferenceError: Cannot access 'x' before initialization
```
