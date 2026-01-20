# 🔥 IMPORTANT JAVASCRIPT ARRAY METHODS (INTERVIEW NOTES)

## 1️⃣ push() – Add element(s) at the **END**

```js
let numbers = [1, 2, 3];
numbers.push(4);
```

### Output:

```js
[1, 2, 3, 4];
```

📌 **Modifies original array**
📌 **Returns new length of array**

💡 **Interview Tip:**
Used when adding new items like chat messages, cart items, logs.

## 2️⃣ pop() – Remove element from the **END**

```js
numbers.pop();
```

### Output:

```js
[1, 2, 3];
```

📌 **Modifies original array**
📌 **Returns removed element**

💡 **Interview Tip:**
Used in stack operations (LIFO – Last In First Out).

## 3️⃣ unshift() – Add element(s) at the **START**

```js
numbers.unshift(0);
```

### Output:

```js
[0, 1, 2, 3];
```

📌 **Modifies original array**
📌 **Returns new length**

⚠️ **Performance Note:**
Slower than `push()` because all elements shift indexes.

## 4️⃣ shift() – Remove element from the **START**

```js
numbers.shift();
```

### Output:

```js
[1, 2, 3];
```

📌 **Modifies original array**
📌 **Returns removed element**

💡 Used in queue operations (FIFO – First In First Out)

## 5️⃣ forEach() – Loop through array

```js
let fruits = ["Apple", "Banana", "Mango"];

fruits.forEach((fruit) => {
  console.log(fruit);
});
```

### Output:

```
Apple
Banana
Mango
```

📌 **Does NOT return anything (returns undefined)**
📌 Cannot be chained like `map()` or `filter()`

💡 **Interview Tip:**
Use `forEach()` for **side effects** (logging, updating UI).

## 6️⃣ map() – Transform array

```js
let numbers = [1, 2, 3];

let doubled = numbers.map((num) => num * 2);
```

### Output:

```js
[2, 4, 6];
```

📌 **Returns a NEW array**
📌 **Original array remains unchanged**

💡 **Interview Favorite Question:**
👉 Difference between `map()` and `forEach()`
✔ `map()` returns array
❌ `forEach()` does not

## 7️⃣ filter() – Filter data by condition

```js
let numbers = [1, 2, 3, 4, 5];

let evenNumbers = numbers.filter((num) => num % 2 === 0);
```

### Output:

```js
[2, 4];
```

📌 **Returns new array**
📌 Skips elements that don’t satisfy condition

💡 Used in search, category filters, dashboards

## 8️⃣ reduce() – Reduce array to single value

```js
let numbers = [1, 2, 3, 4];

let sum = numbers.reduce((total, num) => total + num, 0);
```

### Output:

```js
10;
```

📌 **Returns a single value**
📌 Can return number, string, object, array

💡 **Interview Tip:**
Used for totals, cart price, grouping data.

## 9️⃣ find() – Find first matching element

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

📌 Returns **first match only**
📌 Returns `undefined` if not found

## 🔟 includes() – Check if value exists

```js
let fruits = ["Apple", "Banana"];

fruits.includes("Apple");
```

### Output:

```js
true;
```

📌 Returns boolean (`true / false`)
📌 Case-sensitive

## 1️⃣1️⃣ indexOf() – Get index of element

```js
fruits.indexOf("Banana");
```

### Output:

```js
1;
```

📌 Returns `-1` if not found
📌 Works with primitive values

## 1️⃣2️⃣ slice() – Extract part of array

```js
let arr = [1, 2, 3, 4, 5];

arr.slice(1, 4);
```

### Output:

```js
[2, 3, 4];
```

📌 **Does NOT modify original array**
📌 End index is **exclusive**

💡 Used for pagination, copying arrays

## 1️⃣3️⃣ splice() – Add / Remove / Replace elements

```js
let arr = [1, 2, 3, 4];

arr.splice(1, 2);
```

### Output:

```js
[1, 4];
```

📌 **Modifies original array**
📌 Returns removed elements

💡 **Interview Warning:**
`splice()` mutates data — be careful in React!

## 1️⃣4️⃣ sort() – Sort array

```js
let numbers = [3, 1, 4, 2];

numbers.sort((a, b) => a - b);
```

### Output:

```js
[1, 2, 3, 4];
```

📌 **Modifies original array**
📌 Without callback, sorts as strings ❗

## 1️⃣5️⃣ reverse() – Reverse array

```js
numbers.reverse();
```

### Output:

```js
[4, 3, 2, 1];
```

📌 **Modifies original array**

## 🧠 INTERVIEW QUICK SUMMARY

| Method  | Returns | Mutates Original |
| ------- | ------- | ---------------- |
| push    | length  | ✅               |
| pop     | element | ✅               |
| shift   | element | ✅               |
| unshift | length  | ✅               |
| map     | array   | ❌               |
| filter  | array   | ❌               |
| reduce  | value   | ❌               |
| slice   | array   | ❌               |
| splice  | array   | ✅               |
| sort    | array   | ✅               |
| reverse | array   | ✅               |
