# 🌟 Positive Reviews Average

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Arrays / Filtering / Math

---

## Problem Statement

You are given a list of review ratings (numbers between `0` and `5`).  
Ignore ratings that are **below 3**, and return the **average** of the positive ratings (3 and above), **rounded to 2 decimal places**.

---

## Input Format

An array of numbers (floats or integers) between 0 and 5.

---

## Output Format

A number representing the average of valid (positive) ratings, rounded to 2 decimal places.

---

### Example:

```json
Input: [5, 1.5, 3, 2, 4.2, 1, 3.8]
Output: 4
```

```json
Input: [2.9, 1.8]
Output: 0
```

---

## JavaScript Solution

```js
function solve(input) {
  const validRatings = input.filter(r => r >= 3);
  if (validRatings.length === 0) return 0;

  const sum = validRatings.reduce((acc, val) => acc + val, 0);
  const avg = sum / validRatings.length;
  return parseFloat(avg.toFixed(2));
}
```

---

## Code with Input Handler

```js
function solve(input) {
  const validRatings = input.filter(r => r >= 3);
  if (validRatings.length === 0) return 0;

  const sum = validRatings.reduce((acc, val) => acc + val, 0);
  const avg = sum / validRatings.length;
  return parseFloat(avg.toFixed(2));
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

- Use `.filter()` to keep only ratings `>= 3`.
- If none are valid, return `0`.
- Otherwise, compute average using `.reduce()` and divide by count.
- Round result using `.toFixed(2)` and convert back to number with `parseFloat`.

---

## 🏷️ Tags

`#JavaScript` `#Medium` `#Math` `#Arrays` `#Filter` `#Reduce` `#D9`

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