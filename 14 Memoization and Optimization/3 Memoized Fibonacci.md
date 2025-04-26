# 🐇 Memoized Fibonacci

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 17)  
> **Category:** Recursion | Memoization | Dynamic Programming

---

## 🧩 Problem Statement

You are asked to compute the **Fibonacci number** at position `n`.  
But, the catch is — **use memoization** to make your recursive solution optimized and efficient.

- **Input**: A single number `n`.
- **Output**: The `n-th` Fibonacci number.

---

## 📥 Input Format

```json
n
```

Example:

```json
7
```

---

## 📤 Output Format

```json
13
```

---

## 📌 Important Notes

- Use **recursive** approach.
- **Memoize** previously computed Fibonacci numbers to avoid redundant calculations.
- Remember:
  - Fibonacci(0) = 0
  - Fibonacci(1) = 1
  - Fibonacci(2) = 1
  - Fibonacci(3) = 2
  - and so on...

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const memo = {};

  function fib(n) {
    if (n <= 1) return n;
    if (memo[n]) return memo[n];
    memo[n] = fib(n - 1) + fib(n - 2);
    return memo[n];
  }

  return fib(input);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const memo = {};

  function fib(n) {
    if (n <= 1) return n;
    if (memo[n]) return memo[n];
    memo[n] = fib(n - 1) + fib(n - 2);
    return memo[n];
  }

  return fib(input);
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

- **Recursion** 🔁
- **Memoization** 🧠
- **Dynamic Programming** 🚀
- **Optimization** 🛠️

---

## 🧪 Example Walkthrough

```js
Input:
7

Steps:
- fib(7) = fib(6) + fib(5)
- fib(6) = fib(5) + fib(4)
- fib(5) = fib(4) + fib(3)
- fib(4) = fib(3) + fib(2)
- fib(3) = fib(2) + fib(1)
- fib(2) = fib(1) + fib(0)
- ...memoize values along the way.

Output:
13
```

---

## 🏷️ Tags

`#Recursion` `#Memoization` `#DynamicProgramming` `#Fibonacci` `#Optimization`

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

