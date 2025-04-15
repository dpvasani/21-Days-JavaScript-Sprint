# 🔢 Run-Length Encoding

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint  
> **Category:** String Manipulation

---

## 📝 Problem Statement

Implement **Run-Length Encoding** on the input string. This means you need to compress the string by encoding consecutive characters as a character followed by the count of its occurrences.

### Example:

- **Input:** `"aaabbc"`
- **Output:** `"a3b2c1"`

### Explanation:
- The character `a` appears **3** times, `b` appears **2** times, and `c` appears **1** time.
  
---

## 📥 Input Format

A string `input`.

### Example Input

```json
"aaabbc"
```

---

## 📤 Output Format

A string representing the run-length encoding of the input.

### Example Output

```json
"a3b2c1"
```

---

## 🔒 Constraints

- The input string can contain any printable ASCII characters.
- The length of the string: `1 <= str.length <= 1000`.

---

## 💡 Hints

- Iterate through the string while counting consecutive occurrences of each character.
- For each group of characters, append the character followed by the count to the result.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let result = '';
  let count = 1;

  for (let i = 1; i <= input.length; i++) {
    if (input[i] === input[i - 1]) {
      count++;
    } else {
      result += input[i - 1] + count;
      count = 1;
    }
  }

  return result;
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

`#JavaScript` `#StringManipulation` `#RunLengthEncoding`

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