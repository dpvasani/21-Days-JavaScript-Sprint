# 🗂️ Group Array by Key or Function

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Utility Functions | Object Grouping

---

## 🧩 Problem Statement

Write a utility function `groupBy(arr, keyOrFn)` that groups items in an array into an object based on a specified **key** or a **function return value**.

---

### ✅ Requirements

- If `keyOrFn` is a **string**, group items based on that object property.
- If `keyOrFn` is a **function**, group items based on the value returned by the function.
- Return an object where:
  - Each **key** is a group identifier.
  - Each **value** is an array of grouped items.

Useful for:
- Structuring data by category or type
- Categorizing primitives or objects dynamically

---

## 📥 Input Format

A tuple containing:
1. `arr`: An array of objects or primitive values.
2. `keyOrFn`: Either:
   - A string (e.g., `"type"`)
   - A stringified function (e.g., `"(x => x.length % 2)"`)

### Example Input

```json
[
  [ { "type": "fruit", "name": "apple" }, { "type": "vegetable", "name": "carrot" }, { "type": "fruit", "name": "banana" } ],
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

An object where:
- Keys are derived from the `keyOrFn`.
- Values are arrays of corresponding items.

### Example Output

```json
{
  "fruit": [ { "type": "fruit", "name": "apple" }, { "type": "fruit", "name": "banana" } ],
  "vegetable": [ { "type": "vegetable", "name": "carrot" } ]
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

- **Dynamic grouping** with object keys
- **Type checking** to distinguish string vs function
- **`eval()`** to parse a function from a string

---

### JavaScript Code

```js
function groupBy(arr, keyOrFn) {
  const result = {};

  for (const item of arr) {
    const groupKey = typeof keyOrFn === 'function'
      ? keyOrFn(item)
      : item[keyOrFn];

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
    const groupKey = typeof keyOrFn === 'function'
      ? keyOrFn(item)
      : item[keyOrFn];

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
  const keyOrFn = keyOrFnRaw.startsWith('(')
    ? eval(keyOrFnRaw)
    : keyOrFnRaw;

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

- 🧠 **Dynamic Grouping** using property or function  
- ⚙️ **Eval Execution** for stringified functions  
- 🔍 **Type Detection** for flexible handling

---

## 🏷️ Tags

`#Grouping` `#Closures` `#ObjectManipulation` `#Eval` `#UtilityFunctions`

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


