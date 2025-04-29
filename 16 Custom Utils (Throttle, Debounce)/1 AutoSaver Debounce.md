# 💾 AutoSaver Debounce

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Debounce | Timing | Utility Functions

---

## 🧩 Problem Statement

You're building an **AutoSave** feature in a code editor. To prevent saving the file on **every keystroke**, you need to implement a **debounce mechanism** that triggers the save only after the user has stopped typing for a given delay.

Your task is to implement the `debounce(fn, delay)` utility. The returned function should delay execution of `fn` until after `delay` milliseconds have passed **since the last time it was called**.

---

## 📥 Input Format

- A function `fn` which needs to be debounced.
- An integer `delay` representing the delay (in milliseconds).

---

## 📤 Output Format

- A debounced version of `fn` which ensures only the last call is executed after the delay period.

---

## 📌 Important Notes

- Only the **last call** in a burst of calls should result in the execution of `fn`.
- If `fn` is invoked again within the delay period, the timer resets.
- You're **not responsible** for simulating typing delays or calling the function — this is handled by the test logic.

---

## ✅ JavaScript Solution

We will implement the `debounce` utility using `setTimeout` and `clearTimeout`. Every time the returned function is called, it clears any previously scheduled execution and sets a new timeout.

---

### JavaScript Code:

```js
function debounce(fn, delay) {
  let timer;

  return function (...args) {
    clearTimeout(timer); // Cancel the previous timer
    timer = setTimeout(() => fn(...args), delay); // Schedule a new one
  };
}
```

---

## 📜 Full Code with Input Handler

```js
// Debounce utility function
function debounce(fn, delay) {
  let timer;

  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}

// Please don't touch the code below
function solve(input) {
  const output = [];
  const debouncedLog = debounce((val) => output.push(val), input.delay);

  input.events.forEach((e, idx) => {
    setTimeout(() => debouncedLog(e), input.times[idx]);
  });

  return new Promise((res) =>
    setTimeout(() => res(output), Math.max(...input.times) + input.delay + 10)
  );
}

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

- **Debouncing**: Limits how often a function is called; useful in event-heavy scenarios like keystrokes.
- **setTimeout/clearTimeout**: Used to schedule and cancel delayed function calls.
- **Closures**: The returned function keeps access to `timer` even after `debounce` has finished executing.

---

## 🧪 Example Walkthrough

### Input:

```json
{
  "delay": 200,
  "events": ["A", "B", "C"],
  "times": [0, 100, 250]
}
```

### Execution:

- "A" is called at 0ms → timer set for 200ms.
- "B" is called at 100ms → previous timer cleared, new timer set for 300ms.
- "C" is called at 250ms → previous timer cleared, new timer set for 450ms.

### Output:

```json
["C"]
```

---

## 🏷️ Tags

`#Debounce` `#AsyncTiming` `#JavaScriptUtility` `#Closures`

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

