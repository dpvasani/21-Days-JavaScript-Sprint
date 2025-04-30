
# 🧠 Run a Function Only Once

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Higher-Order Functions | Closures | Memoization

---

## 🧩 Problem Statement

You're building a utility `once(fn)` that ensures a given function `fn` is **only called once**, no matter how many times the returned function is invoked.

---

### ✅ Requirements

- On the **first call**, invoke the function `fn` with arguments and return the result.
- On **subsequent calls**, return the **first result**, ignoring any new arguments.
- Useful for:
  - Initializing single-use services (e.g. DB connection)
  - Running expensive computations once

---

## 📥 Input Format

The environment provides:
- A stringified function body like `"(x) => x * 2"`
- An array of argument arrays (each sub-array represents arguments for one call)

### Example Input

```json
[
  "(x) => x * 2",
  [[5], [10], [20]]
]
```

---

## 📤 Output Format

An array with the result of each call to the wrapped function.

### Example Output

```json
[10, 10, 10]
```

Only the first call uses the real argument (`5 * 2 = 10`). All others reuse the same result.

---

## 🧪 Test Case

### Input

```json
[
  "(x, y) => x + y",
  [[1, 2], [3, 4], [10, 20]]
]
```

### Output

```json
[3, 3, 3]
```

---

## ✅ JavaScript Solution

### Key Concepts:

- **Closure** to retain result state.
- Use a flag (`called`) to check if the function was already executed.
- Store and reuse the **first result**.

---

### JavaScript Code

```js
function once(fn) {
  let called = false;
  let result;

  return function(...args) {
    if (!called) {
      result = fn(...args);
      called = true;
    }
    return result;
  };
}
```

---

## 🧾 Full Code with Input Handler

```js
function once(fn) {
  let called = false;
  let result;

  return function(...args) {
    if (!called) {
      result = fn(...args);
      called = true;
    }
    return result;
  };
}

// Don't touch below this
function solve(input) {
  const [fnBody, calls] = input;
  const originalFn = eval(`(${fnBody})`);
  const onceFn = once(originalFn);
  return calls.map(args => onceFn(...args));
}

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

- ✅ **Closures** for private state  
- 💡 **Memoization** for first result  
- 🛡️ **Function wrapping**

---

## 🏷️ Tags

`#Closures` `#Memoization` `#HigherOrderFunction` `#FunctionalJS`

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