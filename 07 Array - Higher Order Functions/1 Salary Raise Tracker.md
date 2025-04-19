# 💰 Salary Raise Tracker

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Arrays / Math / Rounding

---

## Problem Statement

An HR manager wants to track updated salaries after giving every employee a **10% raise**.

You need to write a function `solve(input)` that takes an array of current salaries and returns an array of **updated salaries**, **rounded to the nearest integer**.

> 💡 Use `Math.round()` to ensure accurate rounding after the percentage increase.

---

## Input Format

An array of integers — current salaries of employees.

### Example:

```json
Input: [50000, 60000, 75000]
Output: [55000, 66000, 82500]
```

---

## Output Format

An array of integers — salaries after a 10% raise and rounding.

---

## JavaScript Solution

```js
function solve(input) {
  return input.map(salary => Math.round(salary * 1.1));
}
```

---

## Code with Test Handler

```js
// Your task is to implement this function
function solve(input) {
  return input.map(salary => Math.round(salary * 1.1));
}

// Please don't remove the code below
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

- The `map()` method processes each salary.
- Each salary is multiplied by `1.1` to apply a 10% raise.
- `Math.round()` ensures the value is a whole number.

---

## 🏷️ Tags

`#JavaScript` `#Arrays` `#Math` `#Rounding` `#Closures`

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
