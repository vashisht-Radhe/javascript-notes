# 📦 JavaScript Arrays

## 1️⃣ What is an Array?

An **Array** in JavaScript is a **data structure** used to **store multiple values in a single variable**, where each value is stored at a **numeric index** (starting from `0`).

👉 Arrays can store:

- Numbers
- Strings
- Objects
- Functions

## 2️⃣ Real-Life Analogy 🧠

### 🚌 Bus Seats Analogy

Think of an array as a **bus with numbered seats**:

| Seat Number (Index) | Passenger (Value) |
| ------------------- | ----------------- |
| 0                   | Alice             |
| 1                   | Bob               |
| 2                   | Charlie           |

- Each seat has **one passenger**
- Seat numbers start from **0**
- we can **add**, **remove**, or **change** passengers

---

## 3️⃣ Why Do We Use Arrays?

Without arrays:

```js
let student1 = "Alice";
let student2 = "Bob";
let student3 = "Charlie";
```

With arrays:

```js
let students = ["Alice", "Bob", "Charlie"];
```

✔ Cleaner

✔ Easier to manage

✔ Powerful built-in methods

## 4️⃣ Creating an Array

### ✅ Using Array Literal (Most Common)

```js
let fruits = ["Apple", "Banana", "Mango"];
```

### ✅ Using Array Constructor (Rarely used)

```js
let numbers = new Array(1, 2, 3);
```

## 5️⃣ Accessing Array Elements

```js
let fruits = ["Apple", "Banana", "Mango"];

console.log(fruits[0]); // Apple
console.log(fruits[2]); // Mango
```

📌 Index always starts from **0**

## 6️⃣ Modifying Array Elements

```js
fruits[1] = "Orange";
console.log(fruits);
```

### Output:

```js
["Apple", "Orange", "Mango"];
```

## 7️⃣ Array Length

```js
console.log(fruits.length);
```

### Output:

```js
3;
```

# 🔥 IMPORTANT ARRAY METHODS

## 8️⃣ push() – Add element at the END

```js
let numbers = [1, 2, 3];
numbers.push(4);
```

### Output:

```js
[1, 2, 3, 4];
```

📌 **Used when adding new data (chat messages, items, etc.)**

---

## 9️⃣ pop() – Remove element from the END

```js
numbers.pop();
```

### Output:

```js
[1, 2, 3];
```

## 🔟 unshift() – Add element at the START

```js
numbers.unshift(0);
```

### Output:

```js
[0, 1, 2, 3];
```

## 1️⃣1️⃣ shift() – Remove element from the START

```js
numbers.shift();
```

### Output:

```js
[1, 2, 3];
```

## 1️⃣2️⃣ forEach() – Loop through array

`forEach()` is an **array method** in JavaScript used to **execute a function once for each element of an array**, in **order**, without returning a new array.

📌 It is mainly used for **performing actions**, not for transforming data

```js
let fruits = ["Apple", "Banana", "Mango"];

fruits.forEach(function (fruit) {
  console.log(fruit);
});
```

### Output:

```
Apple
Banana
Mango
```

📌 **Used for displaying data**

## 1️⃣3️⃣ map() – Transform array

`map()` is an **array method** in JavaScript used to **create a new array by transforming each element** of an existing array using a callback function.

📌 `*map()*` **always returns a new array**
📌 Original array **does NOT change**

```js
let numbers = [1, 2, 3];

let doubled = numbers.map((num) => num * 2);
```

### Output:

```js
[2, 4, 6];
```

📌 **Used in React, Angular, APIs**

## 1️⃣4️⃣ filter() – Filter data based on condition

```js
let numbers = [1, 2, 3, 4, 5];

let evenNumbers = numbers.filter((num) => num % 2 === 0);
```

### Output:

```js
[2, 4];
```

📌 **Used in search, category filters, dashboards**

## 1️⃣5️⃣ reduce() – Reduce array to single value

```js
let numbers = [1, 2, 3, 4];

let sum = numbers.reduce((total, num) => total + num, 0);
```

### Output:

```js
10;
```

📌 **Used for totals, prices, analytics**

## 1️⃣6️⃣ find() – Find first matching element

```js
let users = [
  { id: 1, name: "Amit" },
  { id: 2, name: "Rahul" },
];

let user = users.find((u) => u.id === 2);
```

### Output:

```js
{ id: 2, name: "Rahul" }
```

## 1️⃣7️⃣ includes() – Check if value exists

```js
let fruits = ["Apple", "Banana"];

console.log(fruits.includes("Apple"));
```

### Output:

```js
true;
```

## 1️⃣8️⃣ indexOf()

```js
fruits.indexOf("Banana");
```

### Output:

```js
1;
```

## 1️⃣9️⃣ slice() – Extract part of array

```js
let arr = [1, 2, 3, 4, 5];

arr.slice(1, 4);
```

### Output:

```js
[2, 3, 4];
```

📌 Does NOT change original array

## 2️⃣0️⃣ splice() – Add / Remove / Replace

```js
let arr = [1, 2, 3, 4];

arr.splice(1, 2);
```

### Output:

```js
[1, 4];
```

📌 **Changes original array**

## 2️⃣1️⃣ sort() – Sort array

```js
let numbers = [3, 1, 4, 2];

numbers.sort((a, b) => a - b);
```

### Output:

```js
[1, 2, 3, 4];
```

## 2️⃣2️⃣ reverse()

```js
numbers.reverse();
```

### Output:

```js
[4, 3, 2, 1];
```
