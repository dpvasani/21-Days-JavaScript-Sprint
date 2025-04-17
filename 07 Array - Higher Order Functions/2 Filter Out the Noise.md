# 🔇 Filter Out the Noise

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Arrays / Filtering / Strings

---

## Problem Statement

You're building a chat system that needs to **filter out short/noisy messages**.

Write a function `solve(input)` that filters a list of messages, keeping **only the ones with 5 or more characters**.

> 💡 Messages with fewer than 5 characters should be considered noise and removed.

---

## Input Format

An array of strings — each representing a user message.

### Example:

```json
Input: ["hello", "hi", "yes", "world", "yo", "nice!"]
Output: ["hello", "world", "nice!"]
```

---

## Output Format

An array of strings — only the messages that are at least 5 characters long.

---

## JavaScript Solution

```js
function solve(input) {
  return input.filter(msg => msg.length >= 5);
}
```

---

## Code with Test Handler

```js
// Your task is to implement this function
function solve(input) {
  return input.filter(msg => msg.length >= 5);
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

- `filter()` checks each message.
- Only messages with `msg.length >= 5` are returned in the final array.

---

## 🏷️ Tags

`#JavaScript` `#Filter` `#Strings` `#Arrays` `#Beginner` `#CleanCode`

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
