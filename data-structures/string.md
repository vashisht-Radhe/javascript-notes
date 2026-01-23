# String (JavaScript)

## Definition

A **String** in JavaScript is a **primitive data type** used to represent **textual data**.
It is a **sequence of characters** enclosed in single quotes (`' '`), double quotes (`" "`), or backticks (`` ` ` ``).

```js
let name = "NodeJS";
```

## Why Strings Are Important

Strings are fundamental to both backend and frontend development. They are used to handle almost all forms of textual data, including:

- HTTP request and response bodies
- URLs, route params, and query strings
- Headers, cookies, and session data
- User credentials (before hashing/encryption)
- JWT tokens and authorization headers
- Environment variables and configuration values
- Text-based database fields

## Creating Strings

### 1️⃣ Using Quotes

```js
let a = "Hello";
let b = "World";
```

### 2️⃣ Using Template Literals (Recommended)

```js
let user = "Admin";
let msg = `Welcome ${user}`;
```

### Output

```
Welcome Admin
```

## String Length

```js
let str = "Backend";
console.log(str.length);
```

### Output

```
7
```

## Accessing Characters

```js
let str = "Node";
console.log(str[0]);
console.log(str.charAt(1));
```

### Output

```
N
o
```

## String Immutability 

👉 **Strings are immutable** in JavaScript.
This means **we cannot change a character directly**.

```js
let str = "Hello";
str[0] = "Y";
console.log(str);
```

### Output

```
Hello
```

✅ A **new string** is created when modifications are applied.

## Comparing Strings

```js
console.log("api" === "api");
console.log("API" === "api");
```

### Output

```
true
false
```

👉 String comparison is **case-sensitive**.

## String vs String Object

### Primitive String

```js
let a = "test";
```

### String Object (Avoid)

```js
let b = new String("test");
```

```js
console.log(typeof a);
console.log(typeof b);
```

### Output

```
string
object
```

👉 Interview tip: **Always use primitive strings**, not `new String()`.

## Template Literals (Backend Usage)

Very common in backend for logging and responses.

```js
let method = "GET";
let route = "/users";

console.log(`Request: ${method} ${route}`);
```

### Output

```
Request: GET /users
```

## Strings in Node.js (Example)

```js
function handleRequest(url) {
  if (url === "/login") {
    console.log("Login route");
  }
}

handleRequest("/login");
```
