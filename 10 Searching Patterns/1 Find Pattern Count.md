# 🔍 Find Pattern Count

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 13)  
> **Category:** String Pattern Matching

---

## 🧩 Problem Statement

You're building a basic spam detection feature. Given a paragraph and a keyword, count how many times the keyword (case-insensitive) appears as a separate word in the paragraph.

---

## 📥 Input Format

```js
{
  "paragraph": "The quick brown fox jumps over the lazy dog. The fox is quick.",
  "keyword": "fox"
}
```

---

## 📤 Output Format

Return the count of how many times the keyword appears as a separate word in the paragraph.

```js
3
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { paragraph, keyword } = input;
  
  // Use a regular expression to match the keyword as a separate word (case-insensitive)
  const regex = new RegExp(`\\b${keyword}\\b`, 'gi'); // `\\b` ensures word boundaries
  const matches = paragraph.match(regex);
  
  // If matches found, return the count, else return 0
  return matches ? matches.length : 0;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { paragraph, keyword } = input;
  
  // Use a regular expression to match the keyword as a separate word (case-insensitive)
  const regex = new RegExp(`\\b${keyword}\\b`, 'gi'); // `\\b` ensures word boundaries
  const matches = paragraph.match(regex);
  
  // If matches found, return the count, else return 0
  return matches ? matches.length : 0;
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

- **Regular Expressions:** Used for matching word boundaries with `\\b` and case-insensitive search with `gi` flag.
- **Word Boundary Matching:** Ensures the keyword is matched as a separate word and not part of other words.

---

## 🧪 Example

```js
Input:
{
  "paragraph": "The quick brown fox jumps over the lazy dog. The fox is quick.",
  "keyword": "fox"
}

Output:
2
```

---

## 🏷️ Tags

`#JavaScript` `#StringMatching` `#SpamDetection` `#Easy`

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