# 🧠 Deep Equality of Arrays (`isDeepEqualArray`)

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 10)  
> **Category:** Recursion / Deep Comparison / Arrays

---

## 🧩 Problem Statement

Write a function `isDeepEqualArray` that checks **if two arrays (including nested ones)** are **deeply equal** — meaning:
- They must have the same **length**
- Every corresponding element must be **strictly equal** or **recursively equal** (if arrays)

---

## 📥 Input Format

```js
{
  arr1: [...],
  arr2: [...]
}
```

Where both can contain **nested arrays** of arbitrary depth.

---

## 📤 Output Format

`true` if deeply equal, `false` otherwise.

---

## 🧪 Example

```js
Input:
{
  "arr1": [1, [2, 3], [4, [5]]],
  "arr2": [1, [2, 3], [4, [5]]]
}

Output: true
```

```js
Input:
{
  "arr1": [1, [2, 3], [4, [5]]],
  "arr2": [1, [2, 4], [4, [5]]]
}

Output: false
```

---

## ✅ JavaScript Solution

```js
function isDeepEqualArray(arr1, arr2) {
  if (!Array.isArray(arr1) || !Array.isArray(arr2)) return false;
  if (arr1.length !== arr2.length) return false;

  for (let i = 0; i < arr1.length; i++) {
    const val1 = arr1[i];
    const val2 = arr2[i];

    const bothArrays = Array.isArray(val1) && Array.isArray(val2);
    if (bothArrays) {
      if (!isDeepEqualArray(val1, val2)) return false;
    } else {
      if (val1 !== val2) return false;
    }
  }

  return true;
}
```

---

## 📜 Full Code with Input Handler

```js
function isDeepEqualArray(arr1, arr2) {
  if (!Array.isArray(arr1) || !Array.isArray(arr2)) return false;
  if (arr1.length !== arr2.length) return false;

  for (let i = 0; i < arr1.length; i++) {
    const val1 = arr1[i];
    const val2 = arr2[i];

    const bothArrays = Array.isArray(val1) && Array.isArray(val2);
    if (bothArrays) {
      if (!isDeepEqualArray(val1, val2)) return false;
    } else {
      if (val1 !== val2) return false;
    }
  }

  return true;
}

// Please don't touch the code below
function solve(input) {
  const { arr1, arr2 } = input;
  return isDeepEqualArray(arr1, arr2);
}

const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });
rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- Recursion for nested structures
- Deep comparison strategy
- Type checking using `Array.isArray()`

---

## 🏷️ Tags

`#JavaScript` `#Recursion` `#ArrayComparison` `#NestedArray` `#Hard` `#D10`

---

## 👨‍💻 Author

**Darshan Vasani**  
🚀 Full-Stack Dev | Mentor | Builder  
🌍 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐱 [github.com/dpvasani](https://github.com/dpvasani)

---
