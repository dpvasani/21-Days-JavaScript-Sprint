# 🕒 Work Hours Calculator

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 15)  
> **Category:** Date & Time Handling

---

## 🧩 Problem Statement

You are given:
- An array of **logs**, where each log is an object `{ in: "", out: "" }`.
- Both `in` and `out` are timestamps (ISO 8601 strings).

✅ Your task:  
- Calculate the **total working time** across all logs.
- Return it in the format: `"X hours Y minutes"`

---

## 📥 Input Format

```js
An array of objects:
[
  { in: "2025-04-25T09:00:00Z", out: "2025-04-25T12:30:00Z" },
  { in: "2025-04-25T13:30:00Z", out: "2025-04-25T17:00:00Z" }
]
```

---

## 📤 Output Format

```js
A string in format: "X hours Y minutes"
```

Example:
```js
"7 hours 0 minutes"
```

---

## 📌 Important Notes
- Time must be calculated **accurately**, even across multiple logs.
- Input timestamps are in **UTC** format.
- Handle minutes properly — they are **not** always multiples of 60.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let totalMinutes = 0;

  for (const log of input) {
    const inTime = new Date(log.in);
    const outTime = new Date(log.out);

    const diffMs = outTime - inTime; // difference in milliseconds
    const diffMinutes = diffMs / (1000 * 60); // convert to minutes

    totalMinutes += diffMinutes;
  }

  const hours = Math.floor(totalMinutes / 60);
  const minutes = Math.round(totalMinutes % 60);

  return `${hours} hours ${minutes} minutes`;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  let totalMinutes = 0;

  for (const log of input) {
    const inTime = new Date(log.in);
    const outTime = new Date(log.out);

    const diffMs = outTime - inTime; // milliseconds
    const diffMinutes = diffMs / (1000 * 60);

    totalMinutes += diffMinutes;
  }

  const hours = Math.floor(totalMinutes / 60);
  const minutes = Math.round(totalMinutes % 60);

  return `${hours} hours ${minutes} minutes`;
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

- **Date Object Parsing**
- **Milliseconds to Minutes Conversion**
- **Aggregation of Multiple Intervals**
- **String Formatting**

---

## 🧪 Example

```js
Input:
[
  { in: "2025-04-25T09:00:00Z", out: "2025-04-25T12:30:00Z" },
  { in: "2025-04-25T13:30:00Z", out: "2025-04-25T17:00:00Z" }
]

Output:
"7 hours 0 minutes"
```

---

## 🏷️ Tags

`#JavaScript` `#DateHandling` `#ProblemSolving` `#TimeCalculations`

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