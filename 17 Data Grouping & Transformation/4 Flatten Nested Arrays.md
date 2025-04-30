# 🧮 Flatten Nested Arrays

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 20)  
> **Category:** Array Manipulation | Recursion | Flattening

---

## 🧩 Problem Statement

You're given a **nested array of numbers** (arrays within arrays).  
Your task is to **flatten** this array — transform all nested arrays into a **single array** containing all elements.

For example:

```json
[1, [2, 3], [4, [5, 6]]] → [1, 2, 3, 4, 5, 6]
```

📝 **Note:** The depth of nesting can vary (e.g., multiple levels deep).

---

## 📥 Input Format

A nested array of numbers:

```json
[1, [2, 3], [4, [5, 6]]]
```

---

## 📤 Output Format

A single-level array with all elements:

```json
[1, 2, 3, 4, 5, 6]
```

---

## 🧪 Example

### Input:

```json
[10, [20, 30], [40, [50, [60]]]]
```

### Output:

```json
[10, 20, 30, 40, 50, 60]
```

---

## ✅ JavaScript Solution

### Approach:

- Use **recursion** to handle nested levels.
- If the current element is an array, **recurse** on it.
- If it's a number, add it to the result.
- Alternatively, `Array.prototype.flat(Infinity)` can be used (ES2019+), but the recursive solution is more universal.

---

### JavaScript Code:

```js
function solve(input) {
  const result = [];

  function flatten(arr) {
    for (const item of arr) {
      if (Array.isArray(item)) {
        flatten(item);
      } else {
        result.push(item);
      }
    }
  }

  flatten(input);
  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function solve(input) {
  const result = [];

  function flatten(arr) {
    for (const item of arr) {
      if (Array.isArray(item)) {
        flatten(item);
      } else {
        result.push(item);
      }
    }
  }

  flatten(input);
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

## 🧠 Key Concepts

- **Recursion**: Solving problems by dividing them into smaller subproblems.
- **Array traversal**: Checking each element's type (array or value).
- **Flattening logic**: Deconstruct nested structures into a flat structure.

---

## 🏷️ Tags

`#ArrayFlattening` `#Recursion` `#NestedArrays` `#JavaScriptLogic` `#Intermediate`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---

