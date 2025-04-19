# 🔢 Counter Maker

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 7)  
> **Category:** Closures / Function Factories

---

## Problem Statement

Implement a function `makeCounter(start)` that returns another function.

- The returned function, when called repeatedly, should return incrementing numbers starting from `start`.

---

## Input Format

```json
{
  "start": 5,
  "calls": 4
}
```

---

## Output Format

```json
[5, 6, 7, 8]
```

---

## JavaScript Solution

```js
function makeCounter(start) {
  let current = start;
  return function () {
    return current++;
  };
}

// Please don't touch the code below
function solve(input) {
  const { start, calls } = input;
  const counter = makeCounter(start);
  const output = [];

  for (let i = 0; i < calls; i++) {
    output.push(counter());
  }

  return output;
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

## 🏷️ Tags

`#JavaScript` `#Closures` `#FunctionReturningFunction` `#Encapsulation`

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