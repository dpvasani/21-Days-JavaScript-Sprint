# 🧮 Group Students by Grade

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 20)  
> **Category:** Array Manipulation | Object Grouping | Data Transformation

---

## 🧩 Problem Statement

You're provided with a list of **student records**. Each record contains:

- `name`: the student's name (string)
- `grade`: the student's grade (number)

Your task is to **group** students by their `grade`, returning an object where:

- The keys are **grade numbers**.
- The values are **arrays of student names** who received that grade, **in the original input order**.

📝 **Note:** JavaScript auto-sorts numeric object keys in ascending order when the object is printed or stringified. Your solution should follow this behavior naturally.

---

## 📥 Input Format

An array of student objects:

```json
[
  { "name": "Alice", "grade": 90 },
  { "name": "Bob", "grade": 80 },
  { "name": "Charlie", "grade": 90 }
]
```

---

## 📤 Output Format

An object grouped by grade:

```json
{
  "80": ["Bob"],
  "90": ["Alice", "Charlie"]
}
```

---

## 🧪 Example

### Input:

```json
[
  { "name": "Alice", "grade": 90 },
  { "name": "Bob", "grade": 80 },
  { "name": "Charlie", "grade": 90 },
  { "name": "David", "grade": 80 }
]
```

### Output:

```json
{
  "80": ["Bob", "David"],
  "90": ["Alice", "Charlie"]
}
```

---

## ✅ JavaScript Solution

### Approach:

- Loop through the student array.
- For each student:
  - Use their `grade` as a key in the result object.
  - Push the `name` into the corresponding grade array.
- Initialize the key if it doesn’t exist.

---

### JavaScript Code:

```js
function solve(input) {
  const result = {};

  for (const student of input) {
    const { name, grade } = student;

    if (!result[grade]) {
      result[grade] = [];
    }

    result[grade].push(name);
  }

  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function solve(input) {
  const result = {};

  for (const student of input) {
    const { name, grade } = student;

    if (!result[grade]) {
      result[grade] = [];
    }

    result[grade].push(name);
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

- **Object key grouping**: Dynamically creating object keys.
- **Data transformation**: Input → Grouped output.
- **Preserving input order**: Push to arrays without sorting.

---

## 🏷️ Tags

`#ArrayManipulation` `#ObjectGrouping` `#JavaScriptObjects` `#DataTransformation` `#Fundamentals`

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