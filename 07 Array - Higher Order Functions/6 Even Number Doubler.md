# ✨ Even Number Doubler

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Arrays / Filtering / Mapping

---

## Problem Statement

Given an array of integers, return a new array where:
- **Only even numbers are kept**
- **Each even number is doubled**

Odd numbers should be **excluded** from the final result.

---

## Input Format

An array of integers.

---

## Output Format

An array of integers where each element is a doubled even number.

---

### Example:

```json
Input: [1, 2, 3, 4, 5, 6]
Output: [4, 8, 12]
```

> Explanation:
> - Evens: 2, 4, 6 → Doubled: 4, 8, 12

---

## JavaScript Solution

```js
function solve(input) {
  return input
    .filter(num => num % 2 === 0)
    .map(num => num * 2);
}
```

---

## Code with Input Handler

```js
function solve(input) {
  return input
    .filter(num => num % 2 === 0)
    .map(num => num * 2);
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

- `.filter()` removes odd numbers.
- `.map()` doubles the remaining even numbers.

---

## 🏷️ Tags

`#JavaScript` `#Arrays` `#Filter` `#Map` `#Easy` `#D9`

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
