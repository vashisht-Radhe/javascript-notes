# var, let, and const in JavaScript

In JavaScript, `var`, `let`, and `const` are used to declare variables.  
They differ in **scope**, **hoisting**, **redeclaration**, and **reassignment**.  
A clear understanding of these concepts is essential for writing clean code and for JavaScript interviews.

---



## 1. var (`old way- avoid in modern JS`)

### Definition

`var` is the **oldest way** to declare variables in JavaScript.  
It is **function-scoped** and **hoisted** with an initial value of `undefined`.

---

### Key features

- Function-scoped (not block-scoped)
- Can be redeclared
- Can be reassigned
- Hoisted and initialized with `undefined`
- Creates properties on the global object when declared globally

```javascript
var x = 10;
var x = 20; // allowed
x = 30;

if (true) {
  var y = 5;
}
console.log(y); // 5 (leaks outside the block)
```

```javascript
function testVar() {
  if (true) {
    var x = 10;
  }
  console.log(x); // 10 (x is accessible outside the block because var is function-scoped.)
}

testVar();
```

**Limitations of var**

- No block scope → causes variable leakage
- Allows redeclaration → accidental overwrites
- Hoisting leads to confusing behavior
- Not recommended in modern JavaScript
  
⚠️ *Avoid var unless maintaining legacy code*

---

## 2. let (`modern & recommended`)

### Key features

- Block-scoped ({})
- Cannot be redeclared in the same scope
- Can be reassigned
- Hoisted but not usable before declaration (_Temporal Dead Zone_)

```javascript
let a = 10;
// let a = 20; // Error (Cannot redeclare)
a = 20; // allowed

if (true) {
  let b = 5;
}

console.log(b); // Error (block-scoped)
```

```javascript
function testLet() {
  if (true) {
    let x = 10;
  }
  console.log(x);
}

textLet(); // Error because let is block-scoped x exists only inside the if block.
```

_Correct way with let_

```javascript
function testLetCorrect() {
  let x;
  if (true) {
    x = 10;
  }
  console.log(x);
}

textLetCorrect();
```

---

## 3. const (`Constant reference`)

### Key features

- Block-scoped
- Cannot be redeclared
- Cannot be reassigned
- Must be initialized immediately

```javascript
const pi = 3.14;
// pi = 3.145; // Error

const user = { name: "Alex" };
user.name = "Sam"; // allowed (object content can change)
```

```javascript
function testConst() {
    if(true) {
        const x = 10;
    }
    console.log(x); // ReferenceError
}

textConst(); // Same reason as let: block scope
```

**Important:**

- const means the reference cannot change, not the value inside objects/arrays.

```javascript
const arr = [1, 2];
arr.push(3); // allowed
// arr = [4, 5] // Error
```
