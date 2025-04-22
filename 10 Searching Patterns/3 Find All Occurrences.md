# 🔍 Find All Occurrences

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 13)  
> **Category:** String Matching

---

## 🧩 Problem Statement

Given a string `text` and a substring `pattern`, return all starting indices where the `pattern` appears in `text` (case-sensitive).

---

## 📥 Input Format

```js
{
  "text": "ababababa",
  "pattern": "aba"
}
```

---

## 📤 Output Format

Return an array containing all the starting indices where the `pattern` appears in `text`.

```js
[0, 2, 4]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { text, pattern } = input;
  let indices = [];
  let startIndex = 0;
  
  // Iterate through the text to find all occurrences of the pattern
  while ((startIndex = text.indexOf(pattern, startIndex)) !== -1) {
    indices.push(startIndex);
    startIndex++; // Move start index to avoid infinite loop
  }
  
  return indices;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { text, pattern } = input;
  let indices = [];
  let startIndex = 0;
  
  // Iterate through the text to find all occurrences of the pattern
  while ((startIndex = text.indexOf(pattern, startIndex)) !== -1) {
    indices.push(startIndex);
    startIndex++; // Move start index to avoid infinite loop
  }
  
  return indices;
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

- **`indexOf()` method:** Finds the first occurrence of a substring within a string and returns its index. By repeatedly calling it and incrementing the start index, we can find all occurrences.

---

## 🧪 Example

```js
Input:
{
  "text": "ababababa",
  "pattern": "aba"
}

Output:
[0, 2, 4]
```

---

## 🏷️ Tags

`#JavaScript` `#StringMatching` `#SubstringOccurrences` `#Medium`

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