# 🥇 Medal Ceremony

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 12)  
> **Category:** Array Sorting

---

## 🧩 Problem Statement

You are given an array of athlete scores. Return the scores **sorted in descending order**, just like they would be announced during a medal ceremony.

---

## 📥 Input Format

```js
[50, 80, 90, 70]
```

---

## 📤 Output Format

Return an array sorted in descending order.

```js
[90, 80, 70, 50]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  return input.sort((a, b) => b - a);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  return input.sort((a, b) => b - a);
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- Array sorting using `sort()`
- Custom comparator for descending order
- Numerical comparison in JavaScript

---

## 🧪 Example

```js
Input:
[45, 99, 100, 80, 60]

Output:
[100, 99, 80, 60, 45]
```

---

## 🏷️ Tags

`#JavaScript` `#ArraySorting` `#Easy` `#D12`

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