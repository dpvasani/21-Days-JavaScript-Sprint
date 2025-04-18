# 🗳️ Vote Counter

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Objects / Counting / Arrays

---

## Problem Statement

You are given a list of votes cast for different candidates, for example:  
```js
["Alice", "Bob", "Alice", "Eve", "Alice", "Bob"]
```  
Return an **object** with candidate names as **keys** and their total **vote counts** as values.

---

## Input Format

An array of strings — each string is a candidate name.

---

## Output Format

An object with candidate names as keys and total votes as values.

---

### Example:

```json
Input: ["Alice", "Bob", "Alice", "Eve", "Alice", "Bob"]
Output: { "Alice": 3, "Bob": 2, "Eve": 1 }
```

---

## JavaScript Solution

```js
function solve(input) {
  const voteCount = {};
  for (const name of input) {
    voteCount[name] = (voteCount[name] || 0) + 1;
  }
  return voteCount;
}
```

---

## Code with Input Handler

```js
function solve(input) {
  const voteCount = {};
  for (const name of input) {
    voteCount[name] = (voteCount[name] || 0) + 1;
  }
  return voteCount;
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

- Loop through each name.
- Use an object to keep count for each candidate.
- Initialize count to 0 using `|| 0`, then increment.

---

## 🏷️ Tags

`#JavaScript` `#Medium` `#Objects` `#Counting` `#Arrays` `#Tally` `#D9`

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
