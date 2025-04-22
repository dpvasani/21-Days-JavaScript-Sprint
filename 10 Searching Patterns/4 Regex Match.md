# 🔍 Regex Match

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 13)  
> **Category:** String Matching

---

## 🧩 Problem Statement

You're building a simple search feature. Given a `text` and a regex `pattern` string, return all matches of the regex in the text.

---

## 📥 Input Format

```js
{
  "text": "abc123abc456abc789",
  "regex": "\\d+" // Regular expression pattern to match digits
}
```

---

## 📤 Output Format

Return an array of all matches found in the `text` that match the regex pattern.

```js
["123", "456", "789"]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { text, regex } = input;
  const pattern = new RegExp(regex, 'g'); // 'g' flag to match all occurrences globally
  return text.match(pattern) || [];
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { text, regex } = input;
  const pattern = new RegExp(regex, 'g'); // 'g' flag to match all occurrences globally
  return text.match(pattern) || [];
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

- **`RegExp` constructor:** Used to create a regular expression object dynamically. The `'g'` flag ensures global matching.
- **`match()` method:** Returns an array of all matches for the pattern in the string.

---

## 🧪 Example

```js
Input:
{
  "text": "abc123abc456abc789",
  "regex": "\\d+" // Match sequences of digits
}

Output:
["123", "456", "789"]
```

---

## 🏷️ Tags

`#JavaScript` `#RegularExpressions` `#SearchFeature` `#Medium`

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