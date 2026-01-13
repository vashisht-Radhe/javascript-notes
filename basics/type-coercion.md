# TYPE COERCION

### What is Type Coercion?

**Type Coercion** is JavaScript’s behavior of **automatically converting one data type into another** during operations.

JavaScript is a **loosely / dynamically typed language**, so variables can change types at runtime.

```javascript
"5" + 1; // 51
```

**_Types of Type Coercion_**

1. **Implicit Type Coercion**

Done automatically by JavaScript.

2. **Explicit Type Coercion**

Done manually by the developer.

## 1️⃣ IMPLICIT TYPE COERCION

### 🔸 **_String Coercion_**

Occurs when using `+` with a `string`.

```javascript
"5" + 2; // "52"
2 + "5"; //  "25"
"hi" + true; // "hitrue"
1 + 2 + "5"; // "35"
```

✔ If **any operand is a string**, + converts everything to string.

### 🔸 **Number Coercion**

Occurs with **_mathematical operators_** `except +`.

```javascript
"10" - 5; // 5
"10" * "2"; // 20
"10" / 2; // 5
"10" % 2; // 0
```

**_Special Cases:_**

```javascript
Number(null); // 0
Number(true); // 1
Number(false); // 0
Number(undefined); // NaN
```

### 🔸 **Boolean Coercion**

Used in:

- `if`, `while`
- Logical operators (`&&`, `||`, `!`)

**_Falsy Values (Only These)_**

```javascript
false;
0 - 0;
0n;
("");
null;
undefined;
NaN;
```

**_Everything else is Truthy_**

```javascript
"0"
[]
{}
"false"
```

### 🔸 **Abstract Equality Algorithm (Important)**

```javascript
null == undefined; // true
null == 0; // false
undefined == 0; // false
```

```javascript
[] == ""     // true
[] == 0      // true
"" == 0      // true
```

## 2️⃣ EXPLICIT TYPE COERCION (TYPE CONVERSION)

`Explicit type coercion` means `we intentionally convert a value from one data type to another` using built-in functions or operators.

🔹 **_Why Explicit Type Coercion Is Important_**

- Prevents unexpected bugs
- Makes code clearer and more readable
- Ensures correct calculations and comparisons

_*String → Number*_

```javascript
Number("123"); // 123
parseInt("123"); // 123
parseFloat("12.5"); // 12.5
+"45"; // 45
```

Invaild conversion:

```javascript
Number("abc"); // NaN
```

_*Number → String*_

```javascript
String(100); // "100"
(100).toString(); // "100"
true + ""; // "true"
```

_*Boolean*_

```javascript
Boolean(1); // true
Boolean(0); // false
Boolean(""); // false
Boolean("hi"); // true
```

_*Logical Operators Coercion*_

`Logical operator coercion` happens when logical operators force values to be converted into `truthy` or `falsy` values during evaluation.

Logical operators `return actual values`, not just _`true`_ or _`false`_.

🔹 **_The Logical Operators_**

- && → AND
- || → OR
- ! → NOT

🔹 _&& (AND) Coercion_

`Rule`: Returns the `first falsy value`, otherwise the `last value`.

```javascript
true && "hello"; // "hello"
"h1" && 10; // 10
0 && "test"; //0
"" && 100; // ""
```

🔹 _|| (AND) Coercion_

`Rule`: Returns the `first truthy value`, otherwise the `last value`.

```javascript
false || "hello"; // "hello"
"" || 42; // 42
true || 5; // true
null && "default"; //0
0 && "fallback"; // "fallback"
```

🔹 _! (NOT) Coercion_

`Rule`: Converts value to boolean, then negates it.

```javascript
!true; // false
!0; // true
!"hello"; // false
!!"hello"; // true
!!0; // false
```

`!!` value is a common trick to explicitly convert to _`true`_ / _`false`_
