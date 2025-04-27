# 🛠️ Parallel Promise Runner

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Async/Await | Promises

---

## 🧩 Problem Statement

You are given an array of **async functions** that return **Promises**. Your task is to run them **in parallel** and return their resolved results as an array, just like using `Promise.all()`.

---

## 📥 Input Format

- An array of **async functions**, where each function returns a **Promise**.

---

## 📤 Output Format

- An array of results where each result corresponds to the resolution of the respective Promise from the input functions.

---

## 📌 Important Notes

- You need to run all Promises in **parallel** and collect their results.
- Use **`async/await`** to handle the Promises.
- This is conceptually similar to `Promise.all()` which resolves all Promises in parallel and returns an array of their results.

---

## ✅ JavaScript Solution

The solution uses `Promise.all()` to run all the Promises in parallel and wait for them to resolve. Then we simply return the results.

---

### JavaScript Code:

```js
async function solve(input) {
  // Use Promise.all to run all promises in parallel and collect results
  const results = await Promise.all(input.map(fn => fn()));
  return results; // Return the array of results
}
```

---

## 📜 Full Code with Input Handler

```js
async function solve(input) {
  // Use Promise.all to run all promises in parallel and collect results
  const results = await Promise.all(input.map(fn => fn()));
  return results; // Return the array of results
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', async (line) => {
  const input = eval(line); // expected as array of functions returning Promises
  const result = await solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **`Promise.all()`**: Resolves multiple Promises in parallel and returns an array of their resolved values.
- **`async/await`**: Used to handle asynchronous functions and collect results.

---

## 🧪 Example Walkthrough

### Input:

```js
[
  async () => "Task 1 completed",
  async () => "Task 2 completed",
  async () => "Task 3 completed"
]
```

### Steps:

1. Use `Promise.all()` to run all tasks in parallel.
2. Wait for all tasks to resolve.
3. Collect the results in an array and return it.

### Output:

```js
["Task 1 completed", "Task 2 completed", "Task 3 completed"]
```

---

## 🏷️ Tags

`#AsyncAwait` `#Promises` `#ParallelExecution` `#JavaScript`

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

