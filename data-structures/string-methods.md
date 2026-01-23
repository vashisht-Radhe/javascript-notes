# String Methods (JavaScript)

## Overview

JavaScript provides many built-in **string methods** to manipulate and process text.
Since strings are **immutable**, all string methods **return a new string** and do **not modify the original one**.

## 1️⃣ `toUpperCase()` / `toLowerCase()`

Used for **case-insensitive comparison**.

```js
let role = "Admin";

console.log(role.toLowerCase());
console.log(role.toUpperCase());
```

### Output

```
admin
ADMIN
```

use case:

- Role checks
- Email normalization
- Header comparison

## 2️⃣ `trim()` / `trimStart()` / `trimEnd()`

Removes extra whitespace.

```js
let input = "   nodejs   ";

console.log(input.trim());
```

### Output

```
nodejs
```

use case:

- Cleaning user input
- Preventing invalid credentials

## 3️⃣ `includes()`

Checks if a substring exists.

```js
let token = "Bearer abc123";

console.log(token.includes("Bearer"));
```

### Output

```
true
```

use case:

- Authorization headers
- Keyword checks

## 4️⃣ `startsWith()` / `endsWith()`

Checks string boundaries.

```js
let url = "/api/users";

console.log(url.startsWith("/api"));
console.log(url.endsWith("users"));
```

### Output

```
true
true
```

use case:

- Route matching
- File type validation

## 5️⃣ `slice()`

Extracts a part of a string.

```js
let token = "Bearer xyz123";

console.log(token.slice(7));
```

### Output

```
xyz123
```

use case:

- Extracting tokens
- Parsing headers

## 6️⃣ `substring()`

Similar to `slice()` but does **not support negative indexes**.

```js
let str = "Backend";

console.log(str.substring(0, 4));
```

### Output

```
Back
```

Interview note:

- `slice()` is preferred in real projects.

## 7️⃣ `replace()` / `replaceAll()`

Replaces part of a string.

```js
let msg = "Hello World World";

console.log(msg.replace("World", "Node"));
console.log(msg.replaceAll("World", "Node"));
```

### Output

```
Hello Node World
Hello Node Node
```

use case:

- Sanitization
- Formatting responses

## 8️⃣ `split()`

Converts string into an array.

```js
let data = "name,email,password";

console.log(data.split(","));
```

### Output

```
[ 'name', 'email', 'password' ]
```

use case:

- CSV parsing
- Token handling

## 9️⃣ `charAt()` / Index Access

Access individual characters.

```js
let str = "Node";

console.log(str.charAt(1));
console.log(str[2]);
```

### Output

```
o
d
```

## 🔟 `concat()`

Joins strings together.

```js
let a = "Node";
let b = "JS";

console.log(a.concat(" ", b));
```

### Output

```
Node JS
```
