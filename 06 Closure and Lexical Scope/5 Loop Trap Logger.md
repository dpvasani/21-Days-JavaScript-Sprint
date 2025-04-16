# 🪤 Loop Trap Logger

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 7)  
> **Category:** Closures / Loops / Scoping

---

## Problem Statement

Write a function `createLoggers(n)` that returns an array of `n` functions.

Each function, when called, must return its **own index** (from `0` to `n - 1`) — exactly the value at the time of its creation.

> 💡 This tests your understanding of **closure traps in loops**.

---

## Input Format

A number `n` — the number of logger functions to create.

---

## Output Format

An array of values returned by invoking each logger function once.

### Example:

```json
Input: 5
Output: [0, 1, 2, 3, 4]
```

---

## JavaScript Solution

```js
function createLoggers(n) {
  const result = [];

  for (let i = 0; i < n; i++) {
    result.push(function () {
      return i;
    });
  }

  return result;
}
```

> ✅ Works because `let` is **block scoped** — each iteration of `i` creates a new closure scope.

---

## Alternative using IIFE (for `var` or older environments):

```js
function createLoggers(n) {
  const result = [];

  for (var i = 0; i < n; i++) {
    result.push((function(index) {
      return function() {
        return index;
      };
    })(i));
  }

  return result;
}
```

---

## Code with Test Handler

```js
// Your task is to implement this function
function createLoggers(n) {
  const result = [];

  for (let i = 0; i < n; i++) {
    result.push(function () {
      return i;
    });
  }

  return result;
}

// Please don't touch the code below
function solve(input) {
  const n = input;
  const result = createLoggers(n).map(fn => fn());
  return result;
}

const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  input = JSON.parse(input);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Explanation

- **Closure trap**: When using `var`, the index is shared across all functions.
- **Fix**: Use `let` (block-scoped) or use an **IIFE** to capture the correct value.

---

## 🏷️ Tags

`#JavaScript` `#Closures` `#Loops` `#Scoping` `#Interview` `#Tricky`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me!  
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐙 [github.com/dpvasani](https://github.com/dpvasani)  
💼 [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
📢 [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---
