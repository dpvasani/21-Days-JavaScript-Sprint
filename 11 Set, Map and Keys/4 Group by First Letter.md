# 🔠 Group by First Letter

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 14)  
> **Category:** Object Manipulation, Array Handling

---

## 🧩 Problem Statement

You are given an array of strings.  
Group them into an **object** based on their **first letter**.

- **Keys** of the object → the first letters.
- **Values** → arrays of words starting with that letter.

---

## 📥 Input Format

```js
string[]
```

An array of lowercase words.

Example:
```js
["apple", "banana", "apricot", "blueberry", "cherry"]
```

---

## 📤 Output Format

```js
{ [letter: string]: string[] }
```

An object where keys are first letters and values are arrays of words.

Example:
```js
{
  "a": ["apple", "apricot"],
  "b": ["banana", "blueberry"],
  "c": ["cherry"]
}
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const map = {};

  for (const word of input) {
    const firstLetter = word[0];
    if (!map[firstLetter]) {
      map[firstLetter] = [];
    }
    map[firstLetter].push(word);
  }

  return map;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const map = {};

  for (const word of input) {
    const firstLetter = word[0];
    if (!map[firstLetter]) {
      map[firstLetter] = [];
    }
    map[firstLetter].push(word);
  }

  return map;
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

- **Object Building:** Dynamically creating and updating object keys.
- **First Character Access:** Using `word[0]` to group correctly.
- **Efficient Grouping:** Checking and initializing keys when needed.

---

## 🧪 Example

```js
Input:
["apple", "banana", "apricot", "blueberry", "cherry"]

Output:
{
  "a": ["apple", "apricot"],
  "b": ["banana", "blueberry"],
  "c": ["cherry"]
}
```

---

## 🏷️ Tags

`#JavaScript` `#Objects` `#Grouping` `#ArrayHandling` `#Medium`

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
