# 🔗 Common Elements in Two Lists

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 14)  
> **Category:** Set, Array Manipulation

---

## 🧩 Problem Statement

Given two lists of integers,  
return the **unique common elements** between them.

You must use a **Set** for optimal performance.

---

## 📥 Input Format

```js
[number[][]]
```

An array containing two arrays of integers.

Example:
```js
[[1, 2, 3, 4], [3, 4, 5, 6]]
```

---

## 📤 Output Format

```js
number[]
```

An array of unique common integers, sorted in ascending order.

Example:
```js
[3, 4]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const [a, b] = input;
  const setA = new Set(a);
  const result = [];

  for (const num of b) {
    if (setA.has(num)) {
      result.push(num);
      setA.delete(num); // avoid duplicates
    }
  }

  return result.sort((x, y) => x - y);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const [a, b] = input;
  const setA = new Set(a);
  const result = [];

  for (const num of b) {
    if (setA.has(num)) {
      result.push(num);
      setA.delete(num); // avoid duplicates
    }
  }

  return result.sort((x, y) => x - y);
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

- **Set:** Efficiently checking for existence and uniqueness.
- **Avoiding Duplicates:** Deleting the element from the set after finding it.
- **Sorting:** Ascending order sorting for consistent output.

---

## 🧪 Example

```js
Input:
[[1, 2, 3, 4], [3, 4, 5, 6]]

Output:
[3, 4]
```

---

## 🏷️ Tags

`#JavaScript` `#Set` `#ArrayManipulation` `#Medium` `#Optimization`

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
