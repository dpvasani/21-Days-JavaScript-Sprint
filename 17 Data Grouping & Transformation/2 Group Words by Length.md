# 🧮 Group Words by Length

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 20)  
> **Category:** Array Manipulation | Object Grouping | Data Transformation

---

## 🧩 Problem Statement

You're provided with an array of **words** (strings).  
Your task is to **group** the words based on their **length**, returning an object where:

- The **keys** are word lengths (numbers).
- The **values** are arrays of words having that length, **in the order** they appear in the input.

📝 **Note:** JavaScript naturally sorts numeric object keys in ascending order when stringified. Your output should follow this behavior.

---

## 📥 Input Format

An array of words (strings):

```json
["a", "to", "tea", "go", "map", "at"]
```

---

## 📤 Output Format

An object where keys are word lengths, and values are arrays of words of that length:

```json
{
  "1": ["a"],
  "2": ["to", "go", "at"],
  "3": ["tea", "map"]
}
```

---

## 🧪 Example

### Input:

```json
["hi", "hello", "hey", "yo", "ok", "no"]
```

### Output:

```json
{
  "2": ["hi", "yo", "ok", "no"],
  "5": ["hello"],
  "3": ["hey"]
}
```

---

## ✅ JavaScript Solution

### Approach:

- Initialize an empty object `result`.
- Loop through each word.
- For each word:
  - Get the length using `word.length`.
  - Use that length as the key in the object.
  - If the key doesn’t exist, initialize it with an empty array.
  - Push the word to the respective array.

---

### JavaScript Code:

```js
function solve(input) {
  const result = {};

  for (const word of input) {
    const len = word.length;

    if (!result[len]) {
      result[len] = [];
    }

    result[len].push(word);
  }

  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function solve(input) {
  const result = {};

  for (const word of input) {
    const len = word.length;

    if (!result[len]) {
      result[len] = [];
    }

    result[len].push(word);
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

## 🧠 Key Concepts

- **Dynamic object keys**: Grouping based on computed properties.
- **Preserving input order**: Push without sorting.
- **Basic iteration and transformation**.

---

## 🏷️ Tags

`#ArrayManipulation` `#ObjectGrouping` `#StringLength` `#JavaScriptBasics` `#Fundamentals`

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
