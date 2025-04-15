# 🚫 Vowel Remover

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint 
> **Category:** String Manipulation

---

## 📝 Problem Statement

Radhika wants to clean up some strings by **removing all vowels** (both lowercase and uppercase vowels: `a, e, i, o, u`). Write a function that removes all vowels from a given string and returns the result.

---

## 📥 Input Format

A single string `str` (can contain letters, digits, symbols, etc.).

### Example Input

```json
"Hello World"
```

---

## 📤 Output Format

A string with all vowels removed.

### Example Output

```json
"Hll Wrld"
```

### Explanation

Vowels to remove: `e`, `o` (and their uppercase counterparts) → Result: `Hll Wrld`

---

## 🔒 Constraints

- String length: `1 <= str.length <= 1000`
- Input may contain any printable characters, including punctuation, spaces, and digits.

---

## 💡 Hints

- Use a regular expression to match vowels.
- You can create a set of vowels for easier checking.
- Remove all vowels in one pass using `replace()` or by building a new string.

---

## ✅ JavaScript Solution

```js
function solve(str) {
  return str.replace(/[aeiouAEIOU]/g, ''); // Removes all vowels (case-insensitive)
}

// Don't remove this boilerplate
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

rl.on('line', (input) => {
  const { str } = JSON.parse(input);
  const result = solve(str);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#StringManipulation` `#VowelRemoval`

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