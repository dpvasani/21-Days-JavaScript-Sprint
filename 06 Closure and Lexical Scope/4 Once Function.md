# 🔂 Once Function

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 7)  
> **Category:** Closures / Function Control

---

## Problem Statement

Implement a utility function `once(fn)` that:

- Ensures the passed function `fn` is **only executed once**.
- On subsequent calls, it **returns the result** of the first invocation without calling `fn` again.

---

## Input Format

You’ll receive a number `x`.  
`onceFn(x), onceFn(x + 5), onceFn(x + 10)` will be called.

---

## Output Format

An array showing that `fn` was called once, and same result returned thereafter:

```json
[15, 15, 15]
```

---

## JavaScript Solution

```js
function once(fn) {
  let called = false;
  let result;

  return function (...args) {
    if (!called) {
      result = fn.apply(this, args);
      called = true;
    }
    return result;
  };
}

// Please don't touch the code below
function solve(input) {
  const { x } = input;

  function addTen(x) {
    return x + 10;
  }

  const onceFn = once(addTen);
  return [onceFn(x), onceFn(x + 5), onceFn(x + 10)];
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

## 🧠 Explanation

- We use a `called` flag to ensure `fn` runs only once.
- The first time, we execute `fn` and save the `result`.
- Later calls return the same result without re-executing `fn`.

---

## 🏷️ Tags

`#JavaScript` `#Closures` `#Memoization` `#FunctionControl`

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
