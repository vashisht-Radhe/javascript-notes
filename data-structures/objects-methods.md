# 🔥 JavaScript Object Methods & Advanced Concepts

```js
const user = {
  name: "Bob",
  age: 25,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
    zip: "10001",
  },
};
```

## 1️⃣ `Object.keys()`

### 📖 Definition

Returns an **array of enumerable property names (keys)** of an object.

### Example

```js
Object.keys(user);
```

### Output

```js
["name", "age", "address"];
```

### ✅ Use case

- Looping keys
- Validating required fields
- Dynamic forms / APIs

## 2️⃣ `Object.values()`

### 📖 Definition

Returns an **array of values** of an object.

### Example

```js
Object.values(user);
```

### Output

```js
[
  "Bob",
  25,
  { street: "123 Main St", city: "New York", state: "NY", zip: "10001" },
];
```

### ✅ Use case

- Analytics
- Logs
- Comparisons

## 3️⃣ `Object.entries()`

### 📖 Definition

Returns an **array of `[key, value]` pairs**.

### Example

```js
Object.entries(user);
```

### Output

```js
[
  ["name", "Bob"],
  ["age", 25],
  [
    "address",
    { street: "123 Main St", city: "New York", state: "NY", zip: "10001" },
  ],
];
```

### ✅ Use case

- Convert object → array
- `Object.fromEntries()`
- `map`, `filter`, `reduce`

## 4️⃣ Looping Through Objects

### `for...in` loop

### 📖 Definition

Iterates over **keys (including inherited ones)**.

```js
for (let key in user) {
  console.log(key, user[key]);
}
```

### Output

```js
name Bob
age 25
address { ... }
```

⚠️ **Best practice**

```js
if (user.hasOwnProperty(key)) { ... }
```

## 5️⃣ Check if Property Exists

### `in` operator

```js
"name" in user;
```

### Output

```js
true;
```

### `hasOwnProperty()`

```js
user.hasOwnProperty("name");
```

### Output

```js
true;
```

✔ `in` → includes prototype
✔ `hasOwnProperty` → only own properties

## 6️⃣ Optional Chaining (`?.`) ⭐ (VERY IMPORTANT)

### 📖 Definition

Safely accesses nested properties **without throwing errors**.

### Example

```js
console.log(user.address?.city);
console.log(user.profile?.email);
```

### Output

```js
"New York";
undefined;
```

### ❌ Without optional chaining

```js
user.profile.email; // ❌ TypeError
```

## 7️⃣ Object Destructuring ⭐ (Interview Favorite)

### 📖 Definition

Extract properties into variables.

### Example

```js
const { name, age } = user;
console.log(name, age);
```

### Output

```js
Bob 25
```

### Nested destructuring

```js
const {
  address: { city },
} = user;
console.log(city);
```

### Output

```js
New York
```

## 8️⃣ Spread Operator (`...`) with Objects

### 📖 Definition

Creates a **shallow copy** of an object.

### Example

```js
const updatedUser = {
  ...user,
  age: 30,
};
```

### Output

```js
{ name: "Bob", age: 30, address: { ... } }
```

⚠️ **Shallow copy warning**

```js
updatedUser.address.city = "LA";
console.log(user.address.city);
```

Output:

```js
"LA";
```

## 9️⃣ `Object.assign()`

### 📖 Definition

Copies properties from source objects to a target object (shallow copy).

```js
const clone = Object.assign({}, user);
```

### Output

```js
{ name: "Bob", age: 25, address: { ... } }
```

## 🔟 `Object.create()`

### 📖 Definition

Creates a new object using another object as its **prototype**.

```js
const child = Object.create(user);
console.log(child.name);
```

### Output

```js
"Bob";
```

```js
child.hasOwnProperty("name");
```

Output:

```js
false;
```

## 1️⃣1️⃣ `Object.defineProperty()`

### 📖 Definition

Defines a property with full control.

```js
const obj = {};

Object.defineProperty(obj, "id", {
  value: 101,
  writable: false,
  enumerable: true,
});

obj.id = 200;
console.log(obj.id);
```

### Output

```js
101;
```

✔ Used for **read-only fields**, tokens, IDs

## 1️⃣2️⃣ `Object.defineProperties()`

### 📖 Definition

Defines **multiple properties at once**.

```js
const obj = {};

Object.defineProperties(obj, {
  name: { value: "Bob", writable: true },
  age: { value: 25, writable: false },
});

obj.age = 30;
console.log(obj.age);
```

### Output

```js
25;
```

## 1️⃣3️⃣ `Object.freeze()`

### 📖 Definition

Makes an object **fully immutable**.

```js
Object.freeze(user);
user.name = "Amit";
console.log(user.name);
```

### Output

```js
"Bob";
```

❌ Cannot add
❌ Cannot update
❌ Cannot delete

## 1️⃣4️⃣ `Object.seal()`

### 📖 Definition

Prevents **adding/removing** properties but allows updating existing ones.

```js
Object.seal(user);
user.name = "Amit";
user.newKey = "test";

console.log(user);
```

### Output

```js
{ name: "Amit", age: 25, address: { ... } }
```

## 1️⃣5️⃣ `Object.preventExtensions()`

### 📖 Definition

Stops adding new properties only.

```js
Object.preventExtensions(user);
user.country = "India";
```

### Output

```js
country NOT added
```

## 1️⃣6️⃣ `Object.is()`

### 📖 Definition

Strict comparison (better than `===` in edge cases).

```js
Object.is(NaN, NaN);
Object.is(0, -0);
```

### Output

```js
true;
false;
```

## 1️⃣7️⃣ `Object.fromEntries()`

### 📖 Definition

Converts `[key, value]` array → object.

```js
const arr = [
  ["name", "Bob"],
  ["age", 25],
];
Object.fromEntries(arr);
```

### Output

```js
{ name: "Bob", age: 25 }
```

## 🔥 Real-Life API Example

```js
const apiUser = {
  id: 1,
  profile: {
    name: "Rahul",
    skills: ["JS", "React"],
  },
};

console.log(apiUser.profile?.skills?.[0]);
```

### Output

```js
"JS";
```

✔ Safe
✔ Production-ready
✔ Error-free

## ✅ SUMMARY

| Category    | Must Know             |
| ----------- | --------------------- |
| Access      | keys, values, entries |
| Safety      | optional chaining     |
| Copy        | spread, assign        |
| Control     | defineProperty        |
| Security    | freeze, seal          |
| Conversion  | fromEntries           |
| Inheritance | create                |
