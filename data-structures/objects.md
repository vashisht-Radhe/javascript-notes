# 🧱 JavaScript Objects – Core Concepts

## 1️⃣ What is an Object? (Proper Definition)

An **Object** in JavaScript is a **collection of key–value pairs**, where:

- **Keys (properties)** are strings (or symbols)
- **Values** can be **any data type** (string, number, array, object, function)

📌 Objects are used to **represent real-world entities**

## 2️⃣ Real-Life Analogy 🧠

### 🪪 ID Card Analogy

An object is like an **ID card**:

Name: Rahul  
Age: 25  
City: Delhi

➡️ Each field has:

- **Label** → key
- **Value** → value

## 3️⃣ Why Do We Use Objects?

Without object:

```js
let name = "Rahul";
let age = 25;
let city = "Delhi";
```

With object:

```js
let user = {
  name: "Rahul",
  age: 25,
  city: "Delhi",
};
```

✔ Organized
✔ Real-world modeling
✔ Easy data handling

## 4️⃣ Creating an Object

### ✅ Object Literal (Most Common)

```js
let user = {
  name: "Rahul",
  age: 25,
  isAdmin: false,
};
```

### ✅ Using `new Object()` (Rare)

```js
let user = new Object();
user.name = "Rahul";
```

## 5️⃣ Accessing Object Properties

### Dot Notation

```js
console.log(user.name);
```

### Bracket Notation (Dynamic Keys)

```js
console.log(user["age"]);
```

📌 Use bracket notation for **dynamic keys**

## 6️⃣ Adding / Updating Properties

```js
user.city = "Delhi";
user.age = 26;
```

## 7️⃣ Deleting Properties

```js
delete user.isAdmin;
```

## 8️⃣ Object with Methods

```js
let user = {
  name: "Rahul",
  greet() {
    console.log("Hello " + this.name);
  },
};

user.greet();
```

📌 `this` refers to the **current object**

## 9️⃣ Nested Objects

```js
let user = {
  name: "Rahul",
  address: {
    city: "Delhi",
    pincode: 110001,
  },
};

console.log(user.address.city);
```

## 1️⃣0️⃣ Object Immutability (Important Concept)

```js
const user = { name: "Rahul" };

user.name = "Amit"; // ✅ allowed
user = {}; // ❌ not allowed
```

## 1️⃣1️⃣ Comparing Objects (Interview Trap 🚨)

```js
let a = { x: 1 };
let b = { x: 1 };

console.log(a === b); // false
```

📌 Objects are compared by **reference**

## 1️⃣2️⃣ Object vs Array (Quick Interview)

| Feature   | Object        | Array   |
| --------- | ------------- | ------- |
| Structure | Key–Value     | Indexed |
| Order     | No guarantee  | Ordered |
| Use case  | Real entities | Lists   |
