

# 🧩 Flatten Object Keys

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint  
> **Category:** Object Manipulation, Recursion, Nested Structures

---

## 📝 Problem Statement

You are given a **nested object**. Your task is to **flatten** it into a single-level object where nested keys are **dot-separated**.

---

## 📥 Input Format

A nested JavaScript object.

### Example Input

```json
{
  "a": 1,
  "b": {
    "c": 2,
    "d": {
      "e": 3
    }
  }
}
```

---

## 📤 Output Format

A flattened object with dot-separated keys.

### Example Output

```json
{
  "a": 1,
  "b.c": 2,
  "b.d.e": 3
}
```

---

## 🔒 Constraints

- Values will be either primitive (`number`, `string`, etc.) or nested objects.
- You can assume no arrays or functions are present in the object.
- Depth can be up to 10 levels.

---

## 💡 Hints

- Use recursion to traverse nested objects.
- Maintain the current key path during recursion.
- Append nested keys with a `"."`.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const result = {};

  function flatten(obj, prefix = '') {
    for (const key in obj) {
      const newKey = prefix ? `${prefix}.${key}` : key;
      if (typeof obj[key] === 'object' && obj[key] !== null) {
        flatten(obj[key], newKey);
      } else {
        result[newKey] = obj[key];
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

## 🏷️ Tags

`#JavaScript` `#Recursion` `#Object` `#Flattening` `#NestedStructures`

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