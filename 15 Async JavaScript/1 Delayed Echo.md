# 🛠️ Delayed Echo

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 18)  
> **Category:** Asynchronous Programming | Promises

---

## 🧩 Problem Statement

You're building a **mock API** that simulates a delay before returning results.  

You need to write an **async function** that:
- Takes two parameters: a `string` and a `delay` (in milliseconds).
- Returns a `Promise` that resolves to the string after the specified delay.

---

## 📥 Input Format

```json
["Hello", 1000]
```

---

## 📤 Output Format

```json
"Hello"
```

---

## 📌 Important Notes

- Use **`async/await`** to handle the asynchronous nature of the delay.
- The function should **wait** for the specified delay (in ms) before resolving the promise.

---

## ✅ JavaScript Solution

```js
async function solve(input) {
  const [text, delay] = input;

  // Return a Promise that resolves to 'text' after 'delay' ms
  return new Promise(resolve => setTimeout(() => resolve(text), delay));
}
```

---

## 📜 Full Code with Input Handler

```js
async function solve(input) {
  const [text, delay] = input;

  // Return a Promise that resolves to 'text' after 'delay' ms
  return new Promise(resolve => setTimeout(() => resolve(text), delay));
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', async (line) => {
  const input = JSON.parse(line);
  const result = await solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **Async Functions & Promises** 💡
- **setTimeout for Delay** ⏳
- **Awaiting Promise Resolution** ⏰

---

## 🧪 Example Walkthrough

```js
Input:
["Hello", 1000] // 1 second delay

Steps:
- Wait for 1 second (1000 ms).
- Resolve the promise with the value "Hello".

Output:
"Hello"
```

---

## 🏷️ Tags

`#AsyncProgramming` `#Promises` `#SetTimeout` `#JavaScript` `#MockAPI`

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
