# 🕐 Duration Formatter

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 15)  
> **Category:** Date Handling / String Formatting

---

## 🧩 Problem Statement

You are given a **duration** in **seconds**.

✅ Your task:  
- Format it into a **human-readable string** like:
  ```
  "2 hours, 15 minutes, 0 seconds"
  ```
- **Omit** any unit that is zero — **except when all units are zero**, then show `"0 seconds"`.

---

## 📥 Input Format

```js
An integer representing seconds
```

Example:
```js
8125
```

---

## 📤 Output Format

```js
A formatted string
```

Example:
```js
"2 hours, 15 minutes, 25 seconds"
```

---

## 📌 Important Notes
- If a unit's value is **zero**, skip it in the output.
- **BUT** if the input is **0 seconds**, still return `"0 seconds"`.
- Units are: **hours**, **minutes**, **seconds**.

---

## ✅ JavaScript Solution

```js
(input) {
  if (input === 0) return "0 seconds";

  let seconds = input;
  const result = [];

  const hours = Math.floor(seconds / 3600);
  seconds %= 3600;

  const minutes = Math.floor(seconds / 60);
  seconds %= 60;

  if (hours) {
    result.push(`${hours} hour${hours > 1 ? 's' : ''}`);
  }
  if (minutes) {
    result.push(`${minutes} minute${minutes > 1 ? 's' : ''}`);
  }
  if (seconds) {
    result.push(`${seconds} second${seconds > 1 ? 's' : ''}`);
  }
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  if (input === 0) return "0 seconds";

  let seconds = input;
  const result = [];

  const hours = Math.floor(seconds / 3600);
  seconds %= 3600;

  const minutes = Math.floor(seconds / 60);
  seconds %= 60;

  if (hours) {
    result.push(`${hours} hour${hours > 1 ? 's' : ''}`);
  }
  if (minutes) {
    result.push(`${minutes} minute${minutes > 1 ? 's' : ''}`);
  }
  if (seconds) {
    result.push(`${seconds} second${seconds > 1 ? 's' : ''}`);
  }

  return result.join(', ');
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

- **Time Calculations:**  
  - `1 hour = 3600 seconds`
  - `1 minute = 60 seconds`
- **Conditional String Building:** Only add non-zero parts.

---

## 🧪 Example

```js
Input:
8125

Output:
"2 hours, 15 minutes, 25 seconds"

---

Input:
3600

Output:
"1 hours"

---

Input:
0

Output:
"0 seconds"
```

---

## 🏷️ Tags

`#JavaScript` `#DateHandling` `#StringFormatting` `#TimeConversion`

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

