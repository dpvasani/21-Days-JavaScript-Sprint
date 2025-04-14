# 🌀 Spiral Matrix Print

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 2)  
> **Category:** 2D Arrays, Matrix Traversal

---

## 📝 Problem Statement

Given a **2D matrix**, return all elements in **spiral order**, starting from the **top-left corner**, moving **clockwise**.

---

## 📥 Input Format

A 2D matrix (array of arrays), with equal-sized rows.

### Example Input

```json
[
  [1,  2,  3],
  [4,  5,  6],
  [7,  8,  9]
]
```

---

## 📤 Output Format

An array of numbers in spiral traversal order.

### Example Output

```json
[1, 2, 3, 6, 9, 8, 7, 4, 5]
```

---

## 🔒 Constraints

- Rows and columns: `1 <= m, n <= 100`
- Values are integers.

---

## 💡 Hints

- Use four pointers: `top`, `bottom`, `left`, and `right` to track current boundaries.
- Traverse:
  1. Left ➡️ Right
  2. Top ⬇️ Bottom
  3. Right ⬅️ Left
  4. Bottom ⬆️ Top
- Shrink boundaries after each step.

---

## ✅ JavaScript Solution

```js
function solve(matrix) {
  const result = [];
  if (!matrix.length || !matrix[0].length) return result;

  let top = 0, bottom = matrix.length - 1;
  let left = 0, right = matrix[0].length - 1;

  while (top <= bottom && left <= right) {
    // Traverse from Left to Right
    for (let i = left; i <= right; i++) {
      result.push(matrix[top][i]);
    }
    top++;

    // Traverse from Top to Bottom
    for (let i = top; i <= bottom; i++) {
      result.push(matrix[i][right]);
    }
    right--;

    if (top <= bottom) {
      // Traverse from Right to Left
      for (let i = right; i >= left; i--) {
        result.push(matrix[bottom][i]);
      }
      bottom--;
    }

    if (left <= right) {
      // Traverse from Bottom to Top
      for (let i = bottom; i >= top; i--) {
        result.push(matrix[i][left]);
      }
      left++;
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

`#JavaScript` `#MatrixTraversal` `#2DArrays` `#SpiralOrder`

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