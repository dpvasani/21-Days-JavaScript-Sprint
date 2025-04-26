# 🔑 Unique Customer IDs

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 14)  
> **Category:** Set, Array Manipulation

---

## 🧩 Problem Statement

An online store tracks customer visits by their user IDs. However, due to logging glitches, the same ID may appear multiple times.  
Your task is to return an array of **unique customer IDs**, sorted in **ascending order**, using **Set**.

---

## 📥 Input Format

```js
[number[]]
```

An array of integers representing customer IDs (may contain duplicates).

Example:
```js
[3, 5, 2, 3, 7, 5]
```

---

## 📤 Output Format

```js
[number[]]
```

A sorted array of **unique** customer IDs in ascending order.

Example:
```js
[2, 3, 5, 7]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const uniqueIds = [...new Set(input)];
  uniqueIds.sort((a, b) => a - b);
  return uniqueIds;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const uniqueIds = [...new Set(input)];
  uniqueIds.sort((a, b) => a - b);
  return uniqueIds;
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **Set:** Automatically removes duplicates from an array.
- **Array.sort():** Sorting numbers in ascending order using a compare function.
- **Spread Operator:** Used to convert a Set back to an array.

---

## 🧪 Example

```js
Input:
[3, 5, 2, 3, 7, 5]

Output:
[2, 3, 5, 7]
```

---

## 🏷️ Tags

`#JavaScript` `#Array` `#Set` `#Sorting` `#Easy`

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
