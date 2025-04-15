# ➕ Sum of Even Numbers

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint 
> **Category:** Arrays, Number Filtering

---

## 📝 Problem Statement

You are given an array of integers.  
Your task is to return the **sum of all even numbers** present in the array.

---

## 📥 Input Format

A JSON array of integers.

### Example Input

```json
[1, 2, 3, 4, 5, 6]
```

---

## 📤 Output Format

An integer representing the sum of all even numbers.

### Example Output

```json
12
```

> Because 2 + 4 + 6 = **12**

---

## 🔒 Constraints

- All numbers are integers.
- The array can have up to `10^5` elements.
- Integers range from `-10^6` to `10^6`.

---

## 💡 Hints

- Use `.filter()` to extract even numbers.
- Use `.reduce()` or a loop to compute the sum.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let sum = 0;
  for (let num of input) {
    if (num % 2 === 0) {
      sum += num;
    }
  }
  return sum;
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

`#JavaScript` `#Array` `#EvenNumbers` `#Sum` `#BasicLogic`

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