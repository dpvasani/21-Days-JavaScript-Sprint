# 🎯 Find All Pairs With Target Sum

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 2)  
> **Category:** Arrays, Hashing, Two Sum

---

## 📝 Problem Statement

You are given an **array of integers** and a **target value**.  
Your task is to return **all unique pairs** of numbers from the array that **sum up to the target**.

Each pair must:
- Be in **increasing order** (e.g., `[3, 5]` not `[5, 3]`)
- Be **unique** — no duplicate pairs in the result

---

## 📥 Input Format

A JSON array structured as:

```json
{
  "nums": [number array],
  "target": number
}
```

### Example Input

```json
{
  "nums": [2, 4, 3, 5, 7, -1, 0, 5],
  "target": 6
}
```

---

## 📤 Output Format

A JSON array of unique pairs, sorted by the first element of each pair, each pair in increasing order.

### Example Output

```json
[
  [-1, 7],
  [1, 5],
  [2, 4],
  [3, 3]
]
```

---

## 🔒 Constraints

- Array length ≤ `10^5`
- Values range from `-10^6` to `10^6`
- Return order of pairs is not strict, but each pair must be sorted and unique

---

## 💡 Hints

- Use a **Set** or **Map** to store seen numbers for faster lookup.
- Sort each pair before adding to the result to maintain order.
- Use a `Set<string>` to avoid duplicates (e.g., `'2,4'`).

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const [arr, target] = input;
  const result = [];
  const seen = new Set();
  const used = new Set();

  for (let num of arr) {
    let complement = target - num;
    const pairKey = `${Math.min(num, complement)}:${Math.max(num, complement)}`;

    if (seen.has(complement) && !used.has(pairKey)) {
      result.push([Math.min(num, complement), Math.max(num, complement)]);
      used.add(pairKey);
    }
    seen.add(num);
  }

  return result.sort((a, b) => a[0] - b[0]); // ✅ fixed
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

`#JavaScript` `#TwoSum` `#Hashing` `#Array` `#UniquePairs`

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