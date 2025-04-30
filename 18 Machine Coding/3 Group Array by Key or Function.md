# 🗂️ Group Array by Key or Function

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Utility Functions | Object Grouping

---

## 🧩 Problem Statement

Write a utility function `groupBy(arr, keyOrFn)` that groups items in an array into an object based on a specified **key** or **function**.

---

### ✅ Requirements

- If `keyOrFn` is a **string**, group items by that property.
- If `keyOrFn` is a **function**, use its return value as the group key.
- Return an object where:
  - Each **key** is the group identifier.
  - Each **value** is an array of grouped items.

---

## 📥 Input Format

A tuple of:
1. `arr`: An array of objects or primitive values.
2. `keyOrFn`: Either:
   - A string (e.g., `"type"`)
   - A stringified function (e.g., `"(x => x.length % 2)"`)

### Example Input

```json
[
  [ { type: "fruit", name: "apple" }, { type: "vegetable", name: "carrot" }, { type: "fruit", name: "banana" } ],
  "type"
]
```

or

```json
[
  [ "apple", "banana", "carrot", "date" ],
  "(x => x.length)"
]
```

---

## 📤 Output Format

An object mapping group keys to arrays of items.

### Example Output

```json
{
  "fruit": [ { type: "fruit", name: "apple" }, { type: "fruit", name: "banana" } ],
  "vegetable": [ { type: "vegetable", name: "carrot" } ]
}
```

or

```json
{
  "5": ["apple"],
  "6": ["banana", "carrot"],
  "4": ["date"]
}
```

---

## 🧪 Test Case

### Input

```json
[
  [6.1, 4.2, 6.3],
  "(Math.floor)"
]
```

### Output

```json
{
  "6": [6.1, 6.3],
  "4": [4.2]
}
```

---

## ✅ JavaScript Solution

### 🔑 Key Concepts

- Type checking with `typeof`
- Dynamic property assignment in objects
- Use of `eval()` to reconstruct the function

---

### JavaScript Code

```js
function groupBy(arr, keyOrFn) {
  const result = {};

  for (const item of arr) {
    let groupKey;

    if (typeof keyOrFn === 'function') {
      groupKey = keyOrFn(item);
    } else {
      groupKey = item[keyOrFn];
    }

    if (!result[groupKey]) {
      result[groupKey] = [];
    }

    result[groupKey].push(item);
  }

  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function groupBy(arr, keyOrFn) {
  const result = {};

  for (const item of arr) {
    let groupKey;

    if (typeof keyOrFn === 'function') {
      groupKey = keyOrFn(item);
    } else {
      groupKey = item[keyOrFn];
    }

    if (!result[groupKey]) {
      result[groupKey] = [];
    }

    result[groupKey].push(item);
  }

  return result;
}

// Don't touch below this
function solve(input) {
  const [arr, keyOrFnRaw] = input;
  const keyOrFn = keyOrFnRaw.startsWith('(') ? eval(keyOrFnRaw) : keyOrFnRaw;
  return groupBy(arr, keyOrFn);
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

- 🧠 **Dynamic Grouping**
- 🔍 **Type Checking**
- 🧮 **Eval for Dynamic Functions**

---

## 🏷️ Tags

`#Grouping` `#Recursion` `#ObjectManipulation` `#ArrayUtilities`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me  
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐱 [GitHub](https://github.com/dpvasani) | 👔 [LinkedIn](https://linkedin.com/in/dpvasani56)  
📢 [Topmate](https://topmate.io/dpvasani56) | 🌲 [Linktree](https://linktr.ee/dpvasani56)

---
