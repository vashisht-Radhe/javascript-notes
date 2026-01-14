# JavaScript Operators

Operators are symbols that perform operations on values (operands).

---

## 1. Arithmetic Operators

| Operator | Description    |
| -------- | -------------- |
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |
| `%`      | Modulus        |
| `**`     | Exponentiation |
| `++`     | Increment      |
| `--`     | Decrement      |

```js
5 + 2; // 7
5 % 2; // 1
2 ** 3; // 8

let x = 10;
x++; // 11
x--; // 10
```

## 2. Assignment Operators

| Operator | Example | Meaning      |
| -------- | ------- | ------------ |
| `=`      | x = 5   | `Assign`     |
| `+=`     | x += 2  | `x = x + 2`  |
| `-=`     | x -= 2  | `x = x - 2`  |
| `\*=`    | x \*= 2 | `x = x \* 2` |
| `/=`     | x /= 2  | `x = x / 2`  |
| `%=`     | x %= 2  | `x = x % 2`  |

```js
let a = 10;

a += 5; // 15
a -= 3; // 12
a *= 2; // 24
```

## 3. Comparison Operators

| Operator | Description           |
| -------- | --------------------- |
| `==`     | Equal (type coercion) |
| `===`    | Strict Equal          |
| `!=`     | Not equal             |
| `!==`    | Strict not equal      |
| `>`      | Greater than          |
| `>`      | Less than             |
| `>=`     | Greater or equal      |
| `<=`     | Less or equal         |

```js
5 == "5"; // true
5 === "5"; // false

10 > 5; // true
5 <= 3; // false
```

## 4 . Logical Operators

| Operator | Description |
| -------- | ----------- |
| `&&`     | AND         |
| `        | OR          |
| `!`      | NOT         |

```js
true && false; // false
true || false; // true
!true; // false

"hello" && 10; // 10
0 || "default"; // "default"
```

## 5. Bitwise Operators

| Operator | Description |
| -------- | ----------- |
| `&`      | AND         |
| `        | OR          |
| `^`      | XOR         |
| `~`      | NOT         |
| `<<`     | Left shift  |
| `>>`     | Right shift |

```js
5 & 1; // 1
5 | 1; // 5
5 ^ 1; // 4
~5; // -6

5 << 1; // 10
5 >> 1; // 2
```

## 6. String Operators

```js
"Hello" + " World"; // "Hello World"
```

## 7. Ternary Operator

```js
condition ? value1 : value2;

let age = 18;
let status = age >= 18 ? "Adult" : "Minor";
```

## 8. Type Operators

| Operator   | Description     |
| ---------- | --------------- |
| typeof     | Returns type    |
| instanceof | Checks instance |

```js
typeof 10; // "number"
arr instanceof Array; // true
```

## 9. Nullish Coalescing Operator

```js
let value = null ?? "default"; // "default"

let count = 0 ?? 10; // 0
```

## 10. Optional Chaining Operator

```js
let user = {
  profile: {
    name: "Alex",
  },
};

user?.profile?.name; // "Alex"
user?.address?.city; // undefined
```

## 11. Spread & Rest Operators

```js
const arr = [1, 2, 3];
const copy = [...arr];

function sum(...nums) {
  return nums.reduce((a, b) => a + b);
}
```

## 12. Comma Operator

```js
let x = (1, 2, 3); // 3
```
