# JavaScript Conditionals

Conditionals are used to **make decisions** in code based on conditions that evaluate to `true` or `false`.

---

## 1. if Statement

Executes a block of code **only if** the condition is true.

```js
let age = 20;

if (age >= 18) {
  console.log("You are an adult");
}
```

## 2. if...else Statement

Executes one block if the condition is true, otherwise another.

```js
let age = 16;

if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

## 3. if...else if...else Statement

Used to check multiple conditions.

```js
let marks = 75;

if (marks >= 90) {
  console.log("Grade A");
} else if (marks >= 70) {
  console.log("Grade B");
} else if (marks >= 50) {
  console.log("Grade C");
} else {
  console.log("Fail");
}
```

## 5. switch Statement

Used when comparing one value against many cases.

```js
let day = 3;

switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Invalid day");
}
```
