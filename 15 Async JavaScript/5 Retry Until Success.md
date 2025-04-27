# 🛠️ Retry Until Success

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Async/Await | Retry Logic

---

## 🧩 Problem Statement

You are asked to implement a function that retries a given **async task** until it succeeds, or fails after a given maximum number of attempts. 

If the task **rejects**, retry it.  
If it **resolves**, return the result.  
If all attempts **fail**, throw an error saying "Failed after x attempts".

---

## 📥 Input Format

- `taskFn`: The asynchronous function to be retried.
- `maxAttempts`: The maximum number of attempts to retry the task.

---

## 📤 Output Format

- The result from the `taskFn` if it resolves successfully within `maxAttempts`.
- If the task fails after `maxAttempts`, an error is thrown with the message "Failed after x attempts".

---

## 📌 Important Notes

- You need to retry the `taskFn` on failure.
- If `taskFn` resolves, return the result immediately.
- After `maxAttempts` retries, if the task has not resolved, throw an error.

---

## ✅ JavaScript Solution

We will implement a `retry()` function that attempts to call `taskFn` and retries if it fails. We will track the number of attempts, and if the task resolves, we return the result. If all attempts fail, we throw an error.

---

### JavaScript Code:

```js
async function solve(input) {
  const [taskFn, maxAttempts] = input;

  // Retry function
  async function retry(fn, attempts) {
    let attempt = 0;

    // Loop until max attempts are reached
    while (attempt < attempts) {
      try {
        // Attempt to run the task
        const result = await fn();
        return result; // Return result if successful
      } catch (e) {
        // Increment attempt count on failure
        attempt++;
        if (attempt === attempts) {
          // Throw error if max attempts are reached
          throw new Error(`Failed after ${attempts} attempts`);
        }
      }
    }
  }

  return await retry(taskFn, maxAttempts);
}
```

---

## 📜 Full Code with Input Handler

```js
async function solve(input) {
  const [taskFn, maxAttempts] = input;

  // Retry function
  async function retry(fn, attempts) {
    let attempt = 0;

    // Loop until max attempts are reached
    while (attempt < attempts) {
      try {
        // Attempt to run the task
        const result = await fn();
        return result; // Return result if successful
      } catch (e) {
        // Increment attempt count on failure
        attempt++;
        if (attempt === attempts) {
          // Throw error if max attempts are reached
          throw new Error(`Failed after ${attempts} attempts`);
        }
      }
    }
  }

  return await retry(taskFn, maxAttempts);
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', async (line) => {
  const input = eval(line); // [function, number]
  try {
    const result = await solve(input);
    process.stdout.write(JSON.stringify(result));
  } catch (e) {
    process.stdout.write(JSON.stringify(e.message));
  }
});
```

---

## 🧠 Key Concepts

- **Retry Logic**: Implementing a mechanism to attempt an operation multiple times before deciding to fail.
- **Async/Await**: Used to handle asynchronous functions and retry them upon failure.
- **Error Handling**: We throw an error after all retry attempts have been exhausted.

---

## 🧪 Example Walkthrough

### Input:

```js
[
  async () => { throw new Error("Task failed") },  // Simulating failure
  3  // Max 3 attempts
]
```

### Steps:

1. Retry the task up to 3 times.
2. After 3 failed attempts, throw an error saying: "Failed after 3 attempts".

### Output:

```js
"Failed after 3 attempts"
```

---

## 🏷️ Tags

`#AsyncAwait` `#RetryLogic` `#ErrorHandling` `#JavaScript`

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
