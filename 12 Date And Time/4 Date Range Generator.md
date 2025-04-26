
# 📅 Date Range Generator

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 15)  
> **Category:** Date Handling / Loops

---

## 🧩 Problem Statement

You are given:
- A **start date** and **end date** in `YYYY-MM-DD` format.

✅ Your task:  
- Return an **array** of **date strings** for **each day** from `start` to `end`, inclusive.

---

## 📥 Input Format

```js
An object with:
{
  start: "YYYY-MM-DD",
  end: "YYYY-MM-DD"
}
```

Example:
```js
{
  start: "2025-04-10",
  end: "2025-04-12"
}
```

---

## 📤 Output Format

```js
An array of strings, each string in "YYYY-MM-DD" format
```

Example:
```js
["2025-04-10", "2025-04-11", "2025-04-12"]
```

---

## 📌 Important Notes
- The range is **inclusive** (both `start` and `end` included).
- Dates must be in **ascending order**.
- No time portion — only dates in **string** format.
- Use **UTC-based** date manipulation to avoid timezone issues if needed.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { start, end } = input;
  const startDate = new Date(start);
  const endDate = new Date(end);

  const dates = [];

  while (startDate <= endDate) {
    // Format the date as YYYY-MM-DD
    const year = startDate.getUTCFullYear();
    const month = String(startDate.getUTCMonth() + 1).padStart(2, '0');
    const day = String(startDate.getUTCDate()).padStart(2, '0');

    dates.push(`${year}-${month}-${day}`);

    // Move to next day
    startDate.setUTCDate(startDate.getUTCDate() + 1);
  }

  return dates;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { start, end } = input;
  const startDate = new Date(start);
  const endDate = new Date(end);

  const dates = [];

  while (startDate <= endDate) {
    const year = startDate.getUTCFullYear();
    const month = String(startDate.getUTCMonth() + 1).padStart(2, '0');
    const day = String(startDate.getUTCDate()).padStart(2, '0');

    dates.push(`${year}-${month}-${day}`);

    startDate.setUTCDate(startDate.getUTCDate() + 1);
  }

  return dates;
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

- **Date Parsing and Formatting**  
- **While Loops for Iteration**  
- **UTC Date Handling** to avoid timezone side-effects

---

## 🧪 Example

```js
Input:
{
  start: "2025-04-10",
  end: "2025-04-13"
}

Output:
[
  "2025-04-10",
  "2025-04-11",
  "2025-04-12",
  "2025-04-13"
]
```

---

## 🏷️ Tags

`#JavaScript` `#DateHandling` `#Loops` `#ProblemSolving`

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

