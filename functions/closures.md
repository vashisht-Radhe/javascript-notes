# JavaScript Closures

## 1️⃣ Definition

**Closures** is a feature in JavaScript whre `an inner function remembers and can asccess variables from its outer (lexical) scope even after the outer function has finished execution.`

## 2️⃣ Why Closers Exist

JavaScript use **lexical scoping**, which means:

- Scope is decided _**at the time of writing code**_, not at runtime.
- Inner functions automatically get access to:
  1.  Their own scope
  2.  Outer function's scope
  3.  Global scope

> **Closure**: When a function is created inside another function and is returned or passed around, it remembers the variables from its outer function. This remembered scope is called a closure.

## 3️⃣ Example

```js
function outer() {
  let count = 0;

  function inner() {
    count++;
    console.log(count);
  }
  return inner;
}

const counter = outer();
counter();
counter();
counter();
```

### Output

```txt
1
2
3
```

**🔍 Explanation**

- `outer()` is executed and return `inner`
- Normally, local variables (`count`) should be destroyed
- But `inner()` **still remembers** `count`
- Because **closure keeps a reference**, not a copy

✅ This memory of `count` is the **closure**

## 4️⃣ Data Privacy

Closures are often used to hide data.

```js
function createBankAccount(initialBalance) {
  let balance = initialBalance;

  return {
    deposit(amount) {
  if (amount <= 0) {
    return "Deposit amount must be positive";
  }
  balance += amount;
  return balance;
},
  withdraw(amount) {
  if (amount > balance) {
    return "Insufficient funds";
  }
  balance -= amount;
  return balance;
}
    checkBalance() {
      return balance;
    },
  };
}

const account = createBankAccount(100);

console.log("Your Balance: ", account.checkBalance());
console.log("Deposit money", account.deposit(50));
console.log("Withdraw money", account.withdraw(30));
console.log("Your Balance", account.checkBalance());
```

### Output

```txt
Your Balance: 100
Deposit money: 50
Withdraw money: 30
Your Balance: 120
```

**🔐 Why Closure?**

- balance is private
- Cannot be accessed directly
- Only modified through exposed methods

### 5️⃣ Advantages of Closures

- Data encapsulation
- Data privacy
- Helps in currying
- Helps in memoization
- Used heavily in callbacks & async code

  ### 6️⃣ Disadvantages of Closures

- Higher memory usage
- Variables are not garbage collected easily
- Can cause memory leaks if not handled properly
