# 🍛 Dynamic Curry

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 16)  
> **Category:** Functional Programming | Currying | Recursion

---

## 🧩 Problem Statement

You need to create a **dynamic currying utility** that:

- Accepts a **multi-argument function** `fn` and a **number** `n`.
- Returns a **curried version** of `fn`, which accepts one argument at a time across **chained calls**.
- When **n arguments** have been collected, it should call the **original function** and return the result.

⚡ Example usage:

```js
curry(fn, 3)(a)(b)(c) → should return fn(a, b, c)
```

---

## 📥 Input Format

An object containing:

```json
{
  "args": [1, 2, 3],
  "n": 3
}
```

- `args`: Array of arguments to feed one-by-one.
- `n`: Number of arguments expected.

---

## 📤 Output Format

A single number or the final result after invoking the function with all arguments.

---

## 📌 Important Notes

- **Chained function calls** are mandatory.
- Keep **collecting** arguments until `n` is reached.
- **Then** invoke the **original function**.
- Dynamic number of arguments.

---

## ✅ JavaScript Solution

```js
function curry(fn, n) {
  return function curried(...args) {
    if (args.length === n) {
      return fn(...args);
    }
    return function (arg) {
      return curried(...args, arg);
    };
  };
}
```

---

## 📜 Full Code with Input Handler

```js
function curry(fn, n) {
  return function curried(...args) {
    if (args.length === n) {
      return fn(...args);
    }
    return function (arg) {
      return curried(...args, arg);
    };
  };
}

// Do not touch the code below
function solve(input) {
  const add = (...args) => args.reduce((a, b) => a + b, 0);
  const { args, n } = input;
  let curriedFn = curry(add, n);
  for (let arg of args) {
    curriedFn = curriedFn(arg);
  }
  return curriedFn;
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

- **Currying** 🎯
- **Recursion** 🔁
- **Chained Calls** 🔗
- **Higher-Order Functions** ⚙️
- **Spread Operator** `...args`

---

## 🧪 Example Walkthrough

```js
Input:
{
  "args": [1, 2, 3],
  "n": 3
}

Steps:
1. curry(add, 3)
2. call with 1 -> returns a function
3. call with 2 -> returns a function
4. call with 3 -> now we have [1,2,3]
5. execute add(1,2,3) = 6

Output:
6
```

---

## 🏷️ Tags

`#Currying` `#Closures` `#Recursion` `#JavaScriptFunctions` `#HigherOrderFunctions`

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
