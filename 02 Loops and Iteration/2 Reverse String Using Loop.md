# 🔁 Reverse String Using Loop

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint 
> **Category:** Strings, Loops

---

## 📝 Problem Statement

You are given a string.  
Return the **reversed string using a loop**.

❗️**Do not use** built-in methods like `.reverse()` or `.split().reverse().join()`.

---

## 📥 Input Format

A string input.

### Example Input

```json
"hello"
```

---

## 📤 Output Format

A string, reversed.

### Example Output

```json
"olleh"
```

---

## 🔒 Constraints

- Input string can contain lowercase/uppercase letters, spaces, digits, and symbols.
- Length of the string ≤ `10^4`.

---

## 💡 Hints

- Use a `for` loop to iterate from the end of the string to the beginning.
- Concatenate each character to build the reversed string.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let reversed = "";
  for (let i = input.length - 1; i >= 0; i--) {
    reversed += input[i];
  }
  return reversed;
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

`#JavaScript` `#StringManipulation` `#ForLoop` `#ReverseString`

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