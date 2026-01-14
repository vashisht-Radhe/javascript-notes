# JavaScript Loops

Loops are used to **execute a block of code repeatedly** until a condition is met.

---

## 1. for Loop

Used when the number of iterations is known.

```js
for (let i = 1; i <= 3; i++) {
  console.log(i);
}

// Output:
// 1
// 2
// 3
```

## 2. while Loop

Runs as long as the condition is true.

```js
let i = 1;

while (i <= 3) {
  console.log(i);
  i++;
}

// Output:
// 1
// 2
// 3
```

## 3. do...while Loop

Runs at least once, even if the condition is false.

```js
let i = 6;

do {
  console.log(i);
  i++;
} while (i <= 5);

// Output:
// 6
```

## 4. break Statement

Stops the loop immediately.

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) break;
  console.log(i);
}

// Output:
// 1
// 2
```

## 5. continue Statement

Skips the current iteration.

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i);
}

// Output:
// 1
// 2
// 4
// 5
```

## 6. Nested Loops

A loop inside another loop.

```js
for (let i = 1; i <= 2; i++) {
  let row = "";
  for (let j = 1; j <= 3; j++) {
    row += `${j} `;
  }
  console.log(`Row ${i}: ${row}`);
}

// Output:
// Row 1: 1 2 3
// Row 2: 1 2 3
```
