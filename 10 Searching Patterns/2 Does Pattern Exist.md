# 🔍 Does Pattern Exist?

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 13)  
> **Category:** String Matching

---

## 🧩 Problem Statement

Given a string and a pattern, return `true` if the pattern exists as a contiguous substring (case-sensitive), otherwise return `false`.

---

## 📥 Input Format

```js
{
  "str": "hello world",
  "pattern": "world"
}
```

---

## 📤 Output Format

Return `true` if the pattern exists as a contiguous substring, otherwise return `false`.

```js
true
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { str, pattern } = input;
  
  // Check if the pattern exists in the string using includes() method
  return str.includes(pattern);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { str, pattern } = input;
  
  // Check if the pattern exists in the string using includes() method
  return str.includes(pattern);
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

- **String `includes()` method:** Checks whether a specific substring is contained within a string, returning `true` if found, `false` otherwise.

---

## 🧪 Example

```js
Input:
{
  "str": "hello world",
  "pattern": "world"
}

Output:
true
```

---

## 🏷️ Tags

`#JavaScript` `#StringMatching` `#SubstringCheck` `#Easy`

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