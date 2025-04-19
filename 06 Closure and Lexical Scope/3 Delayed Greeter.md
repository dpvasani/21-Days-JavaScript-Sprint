# 👋 Delayed Greeter

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 7)  
> **Category:** Closures / Function Factory

---

## Problem Statement

Create a function `createGreeters(names)` that takes an array of names and returns an array of functions.

- Each function, when called, should return a greeting like `"Hello, Alice!"`.
- Each greeter must remember its respective name even when called later (closure behavior).

---

## Input Format

```json
["Alice", "Bob", "Charlie"]
```

---

## Output Format

```json
["Hello, Alice!", "Hello, Bob!", "Hello, Charlie!"]
```

---

## JavaScript Solution

```js
function createGreeters(names) {
  return names.map(name => {
    return function () {
      return `Hello, ${name}!`;
    };
  });
}

// Please don't touch the code below
function solve(input) {
  const names = input;
  const greeters = createGreeters(names);
  return greeters.map(fn => fn());
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

- We use `Array.map()` to create a new function for each name.
- Each function "remembers" its `name` due to **closure** — it captures the surrounding lexical environment at creation.

---

## 🏷️ Tags

`#JavaScript` `#Closures` `#map` `#FunctionFactory`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🎓 **Credly:** [credly.com/users/dpvasani57](https://www.credly.com/users/dpvasani57/)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)  

---