# 📚 Library Late Fees

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint 
> **Category:** Basic Logic

---

## 📝 Problem Statement

A local library calculates late fees based on the number of overdue days. The rules for the fee calculation are as follows:

- **0–5 days:** $1 per day.
- **6–10 days:** $1.5 per day.
- **11 or more days:** $2 per day.

Given the number of overdue days, calculate the total fine.

---

## 📥 Input Format

- A single integer representing the number of days the book is overdue.

### Example Input

```json
7
```

---

## 📤 Output Format

- A single integer representing the total fine.

### Example Output

```json
10.5
```

---

## 🔒 Constraints

- The number of overdue days: `0 <= days <= 30`.

---

## 💡 Hints

- Check the number of overdue days and apply the correct fee for the corresponding range of days.
- You can use conditional statements to check the range of overdue days and compute the total fine accordingly.

---

## ✅ JavaScript Solution

```js
function solve(days) {
  if (days <= 0) return 0;
  if (days <= 5) return days * 1;
  if (days <= 10) return days * 1.5; // Fixed the missing condition
  return days * 2;
}


// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const days = JSON.parse(input);
  const result = solve(days);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Logic` `#Math`

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