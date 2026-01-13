# Data Types

### What are Data Type

A data type defines **what kind of value** a variable can hold and **what operations** can be perfomed on it.

*In Javascript, data types are dynamic*

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

Primitive types store `single values` and are `immutable` (*cannot be changed*).

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
if(isLoggedIn) {
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

Used for *very large numbers* beyond safe limit.

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