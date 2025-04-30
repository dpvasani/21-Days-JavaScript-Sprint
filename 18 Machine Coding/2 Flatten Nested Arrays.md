# 🧱 Flatten Nested Arrays

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Recursion | Array Handling

---

## 🧩 Problem Statement

Implement a utility function `flatten(arr)` that takes a **nested array of arbitrary depth** and returns a **new flat array**.

---

### ✅ Requirements

- Recursively **flatten** nested arrays.
- Must not use `Array.prototype.flat()` or any built-in flatting utility.
- The input array may contain:
  - Numbers
  - Strings
  - Booleans
  - Arrays (nested arbitrarily deep)

---

## 📥 Input Format

A nested array of arbitrary values.

### Example Input

```json
[1, [2, [3, [4]], 5]]
```

---

## 📤 Output Format

A single-level flattened array.

### Example Output

```json
[1, 2, 3, 4, 5]
```

---

## 🧪 Test Case

### Input

```json
[true, [42, ["hello", [false, [null]]]], "world"]
```

### Output

```json
[true, 42, "hello", false, null, "world"]
```

---

## ✅ JavaScript Solution

### Key Concepts:

- **Recursion** to go deep into nested structures  
- Use of `Array.isArray()` to distinguish values

---

### JavaScript Code

```js
function flatten(arr) {
  const result = [];

  for (const item of arr) {
    if (Array.isArray(item)) {
      result.push(...flatten(item)); // Recursively flatten
    } else {
      result.push(item); // Push non-array values directly
    }
  }

  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function flatten(arr) {
  const result = [];

  for (const item of arr) {
    if (Array.isArray(item)) {
      result.push(...flatten(item));
    } else {
      result.push(item);
    }
  }

  return result;
}

// Don't touch below this
function solve(input) {
  return flatten(input);
}

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

- 🧬 **Recursion**  
- 📦 **Array Traversal**  
- 🔁 **Spread operator**

---

## 🏷️ Tags

`#Recursion` `#ArrayManipulation` `#NestedArrays` `#Flattening`

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


