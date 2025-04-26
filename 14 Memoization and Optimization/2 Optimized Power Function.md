# ⚡ Optimized Power Function

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 17)  
> **Category:** Recursion | Memoization | Exponentiation

---

## 🧩 Problem Statement

You are dealing with **large number computations**.  
You need to **efficiently compute powers** using recursion and **memoization** to avoid **repeated calculations**.

- **Input**: A base number `x` and an array of powers `[n1, n2, n3, ...]`.
- **Output**: An array of corresponding results `[x^n1, x^n2, x^n3, ...]`.

---

## 📥 Input Format

```json
[base, [power1, power2, power3, ...]]
```

Example:

```json
[2, [3, 4, 3]]
```

---

## 📤 Output Format

```json
[8, 16, 8]
```

---

## 📌 Important Notes

- Use **memoization**: Once `x^n` is calculated, store it.
- Use **recursion**: Define power(n) recursively.
- Avoid redundant computations for the same `n`.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const [x, powers] = input;
  const memo = {};

  function power(n) {
    if (n === 0) return 1;
    if (memo[n]) return memo[n];
    memo[n] = x * power(n - 1);
    return memo[n];
  }

  return powers.map(power);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const [x, powers] = input;
  const memo = {};

  function power(n) {
    if (n === 0) return 1;
    if (memo[n]) return memo[n];
    memo[n] = x * power(n - 1);
    return memo[n];
  }

  return powers.map(power);
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

- **Memoization** 🧠
- **Recursion** 🔁
- **Exponentiation** 📈
- **Performance Optimization** 🚀

---

## 🧪 Example Walkthrough

```js
Input:
[2, [3, 4, 3]]

Steps:
- power(3) → 2 * 2 * 2 = 8 → memo[3] = 8
- power(4) → 2 * power(3) = 2 * 8 = 16 → memo[4] = 16
- power(3) → already memoized → instantly returns 8

Output:
[8, 16, 8]
```

---

## 🏷️ Tags

`#Recursion` `#Memoization` `#Exponentiation` `#Optimization` `#DynamicProgramming`

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
