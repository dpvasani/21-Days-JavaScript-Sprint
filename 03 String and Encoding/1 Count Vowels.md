# 🔤 Count Vowels

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint
> **Category:** String Manipulation

---

## 📝 Problem Statement

Given a string, return the **number of vowels** in it. The check should be **case-insensitive**, meaning it should count both uppercase and lowercase vowels.

---

## 📥 Input Format

A single string.

### Example Input

```json
"Hello World"
```

---

## 📤 Output Format

An integer indicating the number of vowels.

### Example Output

```json
3
```

### Explanation

Vowels present: `e`, `o`, `o` → Total = **3**

---

## 🔒 Constraints

- String length: `1 <= s.length <= 1000`
- Input may contain spaces and punctuation.

---

## 💡 Hints

- Convert the string to lowercase for easy matching.
- Use a set or string to store vowels for lookup.
- Iterate through the string and count matches.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const vowels = "aeiou";
  let count = 0;

  for (let char of input.toLowerCase()) {
    if (vowels.includes(char)) {
      count++;
    }
  }

  return count;
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

## 🏷️ Tags

`#JavaScript` `#String` `#Vowels` `#CharacterCount`

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