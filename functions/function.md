# JavaScript Functions

Functions are `reusable blocks of code` designed to perform a specific task.  
They help make code _**modular, readable, and maintainable**_.

## 1. What is a Function?

A function:

- Performs a specific task
- Can take inputs (parameters)
- Can return an output

## 2. Function Declaration

### Definition

A function declared using the `function` keyword.

### Syntax

```js
function functionName(parameters) {
  // code
}
```

### Example

```js
function greet(name) {
  return `Hello, ${name}`;
}

console.log(greet("Alex"));
```

### Output

```txt
Hello, Alex
```

### Usage

- General purpose functions
- When hoisting is needed

## 3. Function Expression

### Definition

A function assigned to a variable.

### Example

```js
const add = function (a, b) {
  return a + b;
};

console.log(add(3, 4));
```

### Output

```txt
7
```

### Usage

- When functions are treated as values
- Passed as arguments (callbacks)

## 4. Arrow Functions

### Definition

A shorter syntax for writing functions introduced in ES6.

### Syntax

```js
const functionName = (parameters) => {
  // code
};
```

### Example (Basic)

```js
const multiply = (a, b) => {
  return a * b;
};

console.log(multiply(4, 5));
```

### Output

```txt
20
```

### Example (Implicit Return)

If there is **only one expression**, braces and `return` can be omitted.

```js
const square = (n) => n * n;

console.log(square(6));
```

### Output

```txt
36
```

## 5. Parameters vs Arguments

```js
function sum(a, b) {
  // parameters
  return a + b;
}

sum(2, 3); // arguments
```

## 6. Default Parameters

```js
function greet(name = "Guest") {
  return `Hello, ${name}`;
}

console.log(greet());
```

### Output

```txt
Hello, Guest
```

## 7. Return Statement

- Ends function execution
- Sends value back to caller

```js
function isAdult(age) {
  if (age >= 18) {
    return true;
  }
  return false;
}

console.log(isAdult(20));
```

### Output

```txt
true
```

## 8. Arrow Functions vs Normal Functions

| Feature            | Normal Function | Arrow Function       |
| ------------------ | --------------- | -------------------- |
| `this`             | Has its own     | Inherits from parent |
| Hoisting           | Yes             | No                   |
| `arguments` object | Available       | Not available        |
| Syntax             | Verbose         | Short                |

## 9. When NOT to Use Arrow Functions

❌ As object methods

```js
const user = {
  name: "Alex",
  greet: () => {
    console.log(this.name);
  },
};

user.greet(); // undefined
```

✅ Use normal function

```js
const user = {
  name: "Alex",
  greet() {
    console.log(this.name);
  },
};

user.greet();
```

### Output

```txt
Alex
```

## 10. Functions as Values (Callback Example)

```js
function process(fn) {
  fn();
}

process(() => {
  console.log("Callback executed");
});
```

### Output

```txt
Callback executed
```
