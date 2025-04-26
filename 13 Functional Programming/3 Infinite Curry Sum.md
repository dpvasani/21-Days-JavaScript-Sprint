# 🔗 Infinite Curry Sum

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 16)  
> **Category:** Currying | Functions | Infinite Chaining

---

## 🧩 Problem Statement

Write a **curried** `sum(x)` function that allows users to pass an **unknown number of integers** one-by-one using **chained calls**, and **finally call with `null` to get the total sum**.

### Example:

```js
sum(1)(2)(3)(null); // should return 6
sum(10)(-5)(null);  // should return 5
```

---

## 📥 Input Format

An array of numbers followed by `null`:

```js
[1, 2, 3, null]
[10, -5, null]
```

---

## 📤 Output Format

A single number — the final sum.

---

## 📌 Important Notes

- You must **simulate chaining** behavior.
- The chain **must terminate** on receiving `null`.
- Use **`reduce`** method in the driver code to simulate sequential chaining internally.
- **`sum(x)`** must return a **function** that expects the next value, and so on.
- When **`null`** is passed, return the accumulated sum.

---

## ✅ JavaScript Solution

```js
function sum(x) {
  return function next(y) {
    if (y === null) return x;
    return sum(x + y);
  };
}
```

---

## 📜 Full Code with Input Handler

```js
function sum(x) {
  return function next(y) {
    if (y === null) return x;
    return sum(x + y);
  };
}

// Do not touch the code below
function solve(input) {
  const result = input.reduce((acc, val, index) => {
    if (index === 0) return sum(val);
    if (val === null) return acc(null);
    return acc(val);
  }, null);
  return result;
}

const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **Currying** 📦
- **Infinite Chaining** 🔗
- **Higher Order Functions** 🚀
- **Closure Capture** 🧠
- **Handling Termination Condition** (`null`)

---

## 🧪 Example Walkthrough

```js
Input:
[1, 2, 3, null]

Steps:
sum(1) → returns a function waiting for next input
sum(1)(2) → returns sum(3)
sum(3)(3) → returns sum(6)
sum(6)(null) → returns 6

Output:
6
```

---

## 🏷️ Tags

`#JavaScript` `#Currying` `#Closures` `#FunctionalProgramming` `#Chaining`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---
