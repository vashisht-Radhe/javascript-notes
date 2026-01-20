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
```**