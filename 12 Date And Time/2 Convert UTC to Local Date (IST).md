# 🕰️ Convert UTC to Local Date (IST)

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 15)  
> **Category:** Date Handling

---

## 🧩 Problem Statement

You are given a **UTC ISO 8601** date-time string (example: `"2025-04-10T12:00:00Z"`).

✅ Your task:  
- Convert this UTC timestamp to **Indian Standard Time (IST)** (UTC+5 hours 30 minutes).  
- Return the **formatted string**: `"YYYY-MM-DD HH:mm"` in **24-hour format**.

---

## 📥 Input Format

```js
"YYYY-MM-DDTHH:mm:ssZ"
```

Example:
```js
"2025-04-10T12:00:00Z"
```

---

## 📤 Output Format

```js
"YYYY-MM-DD HH:mm"
```

Example:
```js
"2025-04-10 17:30"
```

---

## 📌 Important Notes
- **Do not rely** on system local time.
- Manually add the offset of **+5 hours 30 minutes**.
- Only **Indian Standard Time** (IST) needs to be handled.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const utcDate = new Date(input);

  // IST is UTC + 5 hours 30 minutes
  const istOffsetInMs = (5 * 60 + 30) * 60 * 1000;
  const istDate = new Date(utcDate.getTime() + istOffsetInMs);

  const year = istDate.getUTCFullYear();
  const month = String(istDate.getUTCMonth() + 1).padStart(2, '0');
  const day = String(istDate.getUTCDate()).padStart(2, '0');
  const hours = String(istDate.getUTCHours()).padStart(2, '0');
  const minutes = String(istDate.getUTCMinutes()).padStart(2, '0');

  return `${year}-${month}-${day} ${hours}:${minutes}`;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const utcDate = new Date(input);

  // IST is UTC + 5 hours 30 minutes
  const istOffsetInMs = (5 * 60 + 30) * 60 * 1000;
  const istDate = new Date(utcDate.getTime() + istOffsetInMs);

  const year = istDate.getUTCFullYear();
  const month = String(istDate.getUTCMonth() + 1).padStart(2, '0');
  const day = String(istDate.getUTCDate()).padStart(2, '0');
  const hours = String(istDate.getUTCHours()).padStart(2, '0');
  const minutes = String(istDate.getUTCMinutes()).padStart(2, '0');

  return `${year}-${month}-${day} ${hours}:${minutes}`;
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

- **UTC to IST Conversion:** Adding a manual time offset.
- **Milliseconds Calculation:** `5h 30m = 19800 seconds = 19800 * 1000 ms`.
- **Manual String Formatting:** No dependency on system's local timezone.

---

## 🧪 Example

```js
Input:
"2025-04-10T12:00:00Z"

Output:
"2025-04-10 17:30"

---

Input:
"2025-12-31T23:00:00Z"

Output:
"2026-01-01 04:30"
```

---

## 🏷️ Tags

`#JavaScript` `#DateHandling` `#TimeZoneConversion` `#IST`

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

