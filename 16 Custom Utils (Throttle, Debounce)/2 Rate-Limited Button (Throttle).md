# ⏱️ Rate-Limited Button (Throttle)

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Throttle | Timing | Utility Functions

---

## 🧩 Problem Statement

Imagine you're building a **"Like" button** on a social media platform. Some users may click it rapidly, but the system should only register **one click per fixed duration** to avoid spamming or flooding the backend.

Your task is to implement the `throttle(fn, delay)` utility. The returned function should allow the `fn` function to run **only once in every `delay` milliseconds**, ignoring additional calls during that period.

---

## 📥 Input Format

- A function `fn` which needs to be throttled.
- An integer `delay` representing the minimum time between accepted calls (in milliseconds).

---

## 📤 Output Format

- A throttled version of `fn` that adheres to the rules below.

---

## 📌 Throttle Behavior

- ✅ Call `fn` **immediately** on the first invocation.
- 🚫 Ignore all further calls within the next `delay` ms.
- ⏱️ Allow the **next accepted call only after `delay` ms** from the last accepted one.
- You're **not responsible** for simulating calls — that is handled by the test logic.

---

## ✅ JavaScript Solution

We will use a timestamp to track when `fn` was last invoked. Calls within `delay` milliseconds of the last execution are ignored.

---

### JavaScript Code:

```js
function throttle(fn, delay) {
  let lastCalledTime = -Infinity;

  return function (...args) {
    const now = Date.now();
    if (now - lastCalledTime >= delay) {
      lastCalledTime = now;
      fn(...args);
    }
  };
}
```

---

## 📜 Full Code with Input Handler

```js
// Throttle utility function
function throttle(fn, delay) {
  let lastCalledTime = -Infinity;

  return function (...args) {
    const now = Date.now();
    if (now - lastCalledTime >= delay) {
      lastCalledTime = now;
      fn(...args);
    }
  };
}

// Please don't touch the code below
function solve(input) {
  const result = [];
  const throttledFn = throttle((v) => result.push(v), input.delay);

  input.events.forEach((e, idx) => {
    const timestamp = input.times[idx];
    setTimeout(() => throttledFn(e, timestamp), timestamp);
  });

  return new Promise((res) =>
    setTimeout(() => res(result), Math.max(...input.times) + input.delay + 10)
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

- **Throttling**: Prevents a function from being called more than once in a given time interval.
- **Date.now()**: Used to track the current timestamp.
- **setTimeout**: Used here only in the test logic to simulate event timings.

---

## 🧪 Example Walkthrough

### Input:

```json
{
  "delay": 300,
  "events": ["A", "B", "C", "D"],
  "times": [0, 100, 250, 400]
}
```

### Execution:

- "A" at 0ms → ✅ accepted.
- "B" at 100ms → ❌ ignored (within 300ms window).
- "C" at 250ms → ❌ ignored.
- "D" at 400ms → ✅ accepted (more than 300ms after A).

### Output:

```json
["A", "D"]
```

---

## 🏷️ Tags

`#Throttle` `#RateLimit` `#JavaScriptTiming` `#Closures` `#UtilityFunctions`

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
