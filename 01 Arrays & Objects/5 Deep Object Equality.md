# 🔍 Deep Object Equality

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint  
> **Category:** Recursion, Object Comparison, Deep Equality

---

## 📝 Problem Statement

Write a function that checks whether two JavaScript objects are **deeply equal**. This means:

- You must compare **keys and values** recursively.
- Objects can contain **nested objects** or **arrays**.
- Two objects are deeply equal if all their keys and values (including nested ones) are equal.

---

## 📥 Input Format

An array with **two objects** to be compared:

```json
[
  { "a": 1, "b": { "c": 2 } },
  { "a": 1, "b": { "c": 2 } }
]
```

---

## 📤 Output Format

A boolean value:

```json
true
```

If they are deeply equal, return `true`; otherwise, return `false`.

---

## 🧪 Example

### Input

```json
[
  { "a": [1, 2], "b": { "x": 10 } },
  { "a": [1, 2], "b": { "x": 10 } }
]
```

### Output

```json
true
```

---

### Non-Equal Case Example

```json
[
  { "a": [1, 2], "b": { "x": 10 } },
  { "a": [2, 1], "b": { "x": 10 } }
]
```

#### Output

```json
false
```

---

## 🔒 Constraints

- No `lodash` or built-in `_.isEqual()` functions.
- Can assume no circular references.
- Types include `object`, `array`, `number`, `string`, `boolean`.

---

## 💡 Hints

- Use recursion to compare nested values.
- Arrays must be compared element by element.
- Use `typeof` to distinguish between primitives and objects/arrays.

---

## ✅ JavaScript Solution

```js
function deepEqual(a, b) {
  if (a === b) return true;

  if (typeof a !== 'object' || typeof b !== 'object' || a === null || b === null) {
    return false;
  }

  if (Array.isArray(a) !== Array.isArray(b)) return false;

  const keysA = Object.keys(a);
  const keysB = Object.keys(b);

  if (keysA.length !== keysB.length) return false;

  for (let key of keysA) {
    if (!keysB.includes(key) || !deepEqual(a[key], b[key])) {
      return false;
    }
  }

  return true;
}

function solve(input) {
  const [obj1, obj2] = input;
  return deepEqual(obj1, obj2);
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

`#JavaScript` `#Recursion` `#DeepEquality` `#ObjectComparison` `#ArrayComparison`

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