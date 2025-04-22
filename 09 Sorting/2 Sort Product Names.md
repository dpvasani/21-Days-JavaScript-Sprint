# 🛍️ Sort Product Names

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 12)  
> **Category:** Array Sorting / Strings

---

## 🧩 Problem Statement

You are given a list of product names. Sort them alphabetically **ignoring case**.

---

## 📥 Input Format

```js
["banana", "Apple", "mango", "apple"]
```

---

## 📤 Output Format

Return an array sorted in case-insensitive alphabetical order.

```js
["Apple", "apple", "banana", "mango"]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  return input.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase()));
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  return input.sort((a, b) => a.toLowerCase().localeCompare(b.toLowerCase()));
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

- String comparison with `localeCompare()`
- Case-insensitive sorting
- Array `sort()` with custom comparator

---

## 🧪 Example

```js
Input:
["Zebra", "apple", "Banana", "mango", "apple"]

Output:
["apple", "apple", "Banana", "mango", "Zebra"]
```

---

## 🏷️ Tags

`#JavaScript` `#StringSorting` `#ArrayMethods` `#Easy` `#D12`

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