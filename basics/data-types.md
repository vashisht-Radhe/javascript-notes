# Data Types

### What are Data Type

A data type defines **what kind of value** a variable can hold and **what operations** can be perfomed on it.

_In Javascript, data types are dynamic_

- we don't declare the type
- JavaScript decides it at runtime

```javascript
let x = 10; // number
x = "hello"; // string
```

---

## Classification of Data Types

JavaScript data types are divided into two main categories:

1. Primitive Data Types
2. Non-Primitive (Reference) Data Types

---

## 1. Primitive Data Types

Primitive types store `single values` and are `immutable` (_cannot be changed_).

List of Primitive Types

- `number`
- `string`
- `boolean`
- `undefined`
- `null`
- `bigInt`
- `symbol`

**🔹Number**
Represents numeric values (integer & decimal).

```javascript
let age = 25;
let price = 99.99;
```

Special numeric values:

```javascript
let x = Infinity;
let y = -Infinity;
let z = NaN; // Not a Number
```

**Note**

```javascript
typof NaN; // number
```

**🔹 String**
Represent textual data.

```javascript
let name = "Radhe";
let city = "Faridabad";
let message = `Hello ${name}`;
```

🔹 Boolean
Represent true or false

```javascript
let isLoggedIn = true;
let isAdmin = false;
```

used in condition

```javascript
if (isLoggedIn) {
  console.log("Welcome");
}
```

🔹 Undefiend

```javascript
let x;
console.log(x); // undefined
```

🔹 Null

Represents intetional absence of value.

```javascript
let user = null;

typeof null; // "Object"
```

🔹 BigInt

Used for _very large numbers_ beyond safe limit.

```javascript
let big = 12345678901234567890n;

Number.MAX_SAFE_INTEGER;
```

🔹 Symbol

Used to create unique identifiers.

```javascript
let id1 = Symbol("id");
let id2 = Symbol("id");

id1 = id2; // false
```

`Example`
```javascript
let a = "hello";
let b = a;
b = "world";

console.log(a); // "hello"
console.log(b); // "world"
```

## 2. Non-Primitive (Reference) Data Types

_Non-Primitive_ data types are also called `reference types`. They are `mutable` and are stored by reference, not by value.
*Compared by reference*.

**_Common Non-Primitive Types_**

- Object
- Array
- Function

🔹 Object

Used to store key-value pairs.

```javascript
let person = {
    name="Alice",
    age=25
};
```

🔹 Array

Used to store multiple values in an order list.

```javascript
let tvShows = ["Breaking Bad", "Dark", "Stranger Things"];
```

🔹 Function
A function in JavaScript is `a reusable block of code designed to perform a specific task.

```javascript
function greet() {
  return "Hello";
}
```

_Other non-primitve type:_

🔹 Date

Represent data and time.

```javascript
let today = new Date();
```

🔹 RegExp

Used for pattern matching.

```javascript
let pattern = /abc/i;
```

🔹Map

Stores key-value pairs with any data type as keys.

```javascript
let map = new map();
map.set("name", "Alice");
```

🔹Set

Stores unique values.

```javascript
let set = new set([1, 2, 3]);
```

`Example`
```javascript
let obj1 = { value: 10 };
let obj2 = obj1;

obj2.value = 20;

console.log(obj1.value); // 20
```

---

### type of Operator
used to check data type.

```javascript
typeof 10;          // "number"
typeof "hello";     // "string"
typeof true;        // "boolean"
typeof undefined;   // "undefined"
typeof null;        // "object" ❌
typeof {};          // "object"
typeof [];          // "object"
typeof function(){} // "function"
```