# 🔗 Compose All

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 16)  
> **Category:** Functional Programming | Composition | Array Handling

---

## 🧩 Problem Statement

You are building a utility that **composes multiple unary functions** together.

Write a function `composeAll(funcs)` that:

- Takes an array of functions `[f1, f2, ..., fn]`.
- Returns a **new function** that, when called with a value `x`, applies the functions from **right to left** in order.

✅ The rightmost function should apply first.

---

## 📥 Input Format

An object with two keys:

```json
{
  "funcs": ["x => x + 1", "x => x * 2"],
  "x": 3
}
```

- `funcs`: An array of functions (given as strings).
- `x`: A number.

---

## 📤 Output Format

A single number — the final result after applying all the functions.

---

## 📌 Important Notes

- **Right to left** composition matters.
- The input functions are given as **strings** and must be **evaluated** using `eval()`.
- **Unary** means each function takes exactly **one input**.
- You must return a **new composed function**.

---

## ✅ JavaScript Solution

```js
function composeAll(funcs) {
  return function(x) {
    return funcs.reduceRight((acc, fn) => fn(acc), x);
  };
}
```

---

## 📜 Full Code with Input Handler

```js
function composeAll(funcs) {
  return function(x) {
    return funcs.reduceRight((acc, fn) => fn(acc), x);
  };
}

// Do not touch the code below
function solve(input) {
  const { funcs, x } = input;
  const fnList = funcs.map(f => eval(f));
  const composed = composeAll(fnList);
  return composed(x);
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

- **Function Composition** 🔗
- **Higher-Order Functions** 🚀
- **`reduceRight`** to apply from right to left
- **Currying Concepts** ✨

---

## 🧪 Example Walkthrough

```js
Input:
{
  "funcs": ["x => x + 1", "x => x * 2"],
  "x": 3
}

Steps:
1. Evaluate functions:
   - f1: x => x + 1
   - f2: x => x * 2

2. Compose:
   - Start with x = 3
   - Apply f2: (3 * 2) = 6
   - Apply f1: (6 + 1) = 7

Output:
7
```

---

## 🏷️ Tags

`#JavaScript` `#FunctionComposition` `#reduceRight` `#Closures` `#HigherOrderFunctions`

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

\