# 👥 Sort by Age

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 12)  
> **Category:** Array Sorting / Objects

---

## 🧩 Problem Statement

You are given a list of users where each user has a `name` and an `age`.  
Sort the users in **ascending order of age**.

---

## 📥 Input Format

```js
[
  { name: "Alice", age: 25 },
  { name: "Bob", age: 22 },
  { name: "Charlie", age: 30 }
]
```

---

## 📤 Output Format

Return an array of user objects sorted by the `age` field in ascending order.

```js
[
  { name: "Bob", age: 22 },
  { name: "Alice", age: 25 },
  { name: "Charlie", age: 30 }
]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  return input.sort((a, b) => a.age - b.age);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  return input.sort((a, b) => a.age - b.age);
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

- Sorting array of objects
- Custom comparator in `sort()`
- Numerical comparison

---

## 🧪 Example

```js
Input:
[
  { name: "Emma", age: 40 },
  { name: "Liam", age: 20 },
  { name: "Olivia", age: 35 }
]

Output:
[
  { name: "Liam", age: 20 },
  { name: "Olivia", age: 35 },
  { name: "Emma", age: 40 }
]
```

---

## 🏷️ Tags

`#JavaScript` `#ArraySorting` `#Objects` `#Medium` `#D12`

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