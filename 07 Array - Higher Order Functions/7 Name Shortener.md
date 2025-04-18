# ✂️ Name Shortener

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Strings / Arrays / Transformation

---

## Problem Statement

You receive a list of full names (e.g., `"John Doe"`).  
Return a list of **first names only**, all in **lowercase**.

---

## Input Format

An array of strings, where each string is a full name.

---

## Output Format

An array of strings containing the **lowercased first names**.

---

### Example:

```json
Input: ["John Doe", "Alice Smith", "Bob Marley"]
Output: ["john", "alice", "bob"]
```

---

## JavaScript Solution

```js
function solve(input) {
  return input.map(name => name.split(" ")[0].toLowerCase());
}
```

---

## Code with Input Handler

```js
function solve(input) {
  return input.map(name => name.split(" ")[0].toLowerCase());
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

- `.split(" ")` gets the first name.
- `.toLowerCase()` ensures it's all lowercase.
- `.map()` applies this to the entire array.

---

## 🏷️ Tags

`#JavaScript` `#Strings` `#Arrays` `#Transformation` `#Lowercase` `#Easy` `#D9`

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
