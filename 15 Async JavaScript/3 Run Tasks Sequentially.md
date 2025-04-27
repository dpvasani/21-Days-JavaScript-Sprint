# 🛠️ Run Tasks Sequentially

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Async/Await | Promises

---

## 🧩 Problem Statement

You’re given an array of **async tasks** (functions that return Promises). 

Your task is to write a function that runs them **one after another**, collects their results, and returns an array of all results in order.

Each task returns a **Promise** that resolves to a **string**.

---

## 📥 Input Format

- An array of functions, where each function returns a Promise that resolves to a string.

---

## 📤 Output Format

- An array of results in the order that the tasks were run.

---

## 📌 Important Notes

- You need to run the tasks **sequentially** — each task should start only after the previous one has finished.
- Use **`async/await`** to handle the Promises.

---

## ✅ JavaScript Solution

To solve this, we will:

1. Use `async/await` to wait for each task to resolve before moving to the next.
2. Collect the results of each task in an array and return it.

---

### JavaScript Code:

```js
async function solve(input) {
  const results = [];
  
  // Loop through each task in the input array and await its result
  for (const task of input) {
    const result = await task();  // Call the task function and wait for its result
    results.push(result);  // Store the result in the results array
  }
  
  return results;  // Return the array of results
}
```

---

## 📜 Full Code with Input Handler

```js
async function solve(input) {
  const results = [];
  
  // Loop through each task in the input array and await its result
  for (const task of input) {
    const result = await task();  // Call the task function and wait for its result
    results.push(result);  // Store the result in the results array
  }
  
  return results;  // Return the array of results
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

- **`async/await`** for handling asynchronous code.
- **Sequential execution of Promises** using `await`.
- **Storing results** in an array.

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

1. Call the first task (`Task 1`), and wait for its Promise to resolve, adding its result to the results array.
2. Call the second task (`Task 2`), and wait for its result.
3. Call the third task (`Task 3`), and collect its result.

### Output:

```js
["Task 1 completed", "Task 2 completed", "Task 3 completed"]
```

---

## 🏷️ Tags

`#AsyncAwait` `#Promises` `#SequentialExecution` `#JavaScript`

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
