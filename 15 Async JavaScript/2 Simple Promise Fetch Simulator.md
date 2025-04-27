# 🛠️ Simple Promise Fetch Simulator

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Promises | Async Programming

---

## 🧩 Problem Statement

You need to simulate **fetching data from an API** using **Promises**.

Given an object with a `status` field:
- If the `status` is `'ok'`, resolve the Promise with `"Success"`.
- If the `status` is anything else, reject the Promise with `"Error"`.

---

## 📥 Input Format

```json
{ "status": "ok" }
```

---

## 📤 Output Format

- If `status` is `'ok'`: `"Success"`
- Otherwise: `"Error"`

---

## 📌 Important Notes

- Use **`async/await`** to handle the asynchronous Promise logic.
- Handle both **resolve** and **reject** properly based on the value of `status`.

---

## ✅ JavaScript Solution

```js
async function solve(input) {
  if (input.status === 'ok') {
    // Resolve the Promise with "Success" if status is 'ok'
    return "Success";
  } else {
    // Reject the Promise with "Error" otherwise
    throw "Error";
  }
}
```

---

## 📜 Full Code with Input Handler

```js
async function solve(input) {
  if (input.status === 'ok') {
    // Resolve the Promise with "Success" if status is 'ok'
    return "Success";
  } else {
    // Reject the Promise with "Error" otherwise
    throw "Error";
  }
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', async (line) => {
  const input = JSON.parse(line);
  try {
    const result = await solve(input);
    process.stdout.write(JSON.stringify(result));
  } catch (e) {
    process.stdout.write(JSON.stringify(e));
  }
});
```

---

## 🧠 Key Concepts

- **Async Functions & Promises** 💡
- **`resolve` and `reject`** in Promises ⚖️
- **Error Handling with `throw`** 🚨

---

## 🧪 Example Walkthrough

```js
Input:
{ "status": "ok" }

Steps:
- Check if the status is 'ok'.
- If yes, resolve the promise with "Success".

Output:
"Success"
```

```js
Input:
{ "status": "fail" }

Steps:
- Check if the status is 'ok'.
- If no, reject the promise with "Error".

Output:
"Error"
```

---

## 🏷️ Tags

`#Promises` `#AsyncProgramming` `#ErrorHandling` `#JavaScript` `#API` 

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
