# 🧮 Nested Loop Product Sum

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint 
> **Category:** Recursion, Arrays

---

## 📝 Problem Statement

You are given a **nested array of numbers**. Each sub-array can contain either numbers or more nested arrays. Return the **product sum**, where the sum of elements at each level is multiplied by its **depth level**.

---

## 📥 Input Format

An array of integers and/or nested arrays.

### Example Input

```json
[1, [2, [3]]]
```

---

## 📤 Output Format

An integer representing the product sum of the nested array.

### Example Output

```json
14
```

### Explanation

- Level 1: `1` → `1 × 1 = 1`  
- Level 2: `2` → `2 × 2 = 4`  
- Level 3: `3` → `3 × 3 = 9`  
- Total = `1 + 4 + 9 = 14`

---

## 🔒 Constraints

- Maximum depth: `<= 10`
- Total elements in all levels: `<= 1000`

---

## 💡 Hints

- Use recursion to dive into nested levels.
- Multiply sum at each level by its depth.
- Base case: if element is a number, return as-is.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  function helper(arr, depth = 1) {
    let sum = 0;
    for (let val of arr) {
      if (Array.isArray(val)) {
        sum += helper(val, depth + 1);
      } else {
        sum += val * depth;
      }
    }
    return sum;
  }
  
  return helper(input);
}


// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});

---

## 🏷️ Tags

`#JavaScript` `#Recursion` `#NestedArrays` `#DepthFirst` `#ProductSum`

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