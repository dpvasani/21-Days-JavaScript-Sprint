# 🔎 Memoized isPrime Checker

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 17)  
> **Category:** Math | Memoization | Optimization

---

## 🧩 Problem Statement

You need to implement an efficient utility to **check if numbers are prime**.  
Since there will be many repeated checks, optimize your solution by **memoizing** the results.

- **Input**: An array of numbers.
- **Output**: An array of booleans indicating whether each number is prime (`true` or `false`).

---

## 📥 Input Format

```json
[number1, number2, number3, ...]
```

Example:

```json
[2, 3, 4, 5, 9]
```

---

## 📤 Output Format

```json
[true, true, false, true, false]
```

---

## 📌 Important Notes

- Use **memoization** to store previously computed prime results.
- A **prime number** is a number greater than 1 with exactly two divisors: 1 and itself.
- Only check divisibility up to the square root (`√n`) for efficiency.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const memo = {};

  function isPrime(n) {
    if (n in memo) return memo[n];
    if (n < 2) return (memo[n] = false);
    for (let i = 2; i * i <= n; i++) {
      if (n % i === 0) {
        memo[n] = false;
        return false;
      }
    }
    memo[n] = true;
    return true;
  }

  return input.map(isPrime);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const memo = {};

  function isPrime(n) {
    if (n in memo) return memo[n];
    if (n < 2) return (memo[n] = false);
    for (let i = 2; i * i <= n; i++) {
      if (n % i === 0) {
        memo[n] = false;
        return false;
      }
    }
    memo[n] = true;
    return true;
  }

  return input.map(isPrime);
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

- **Prime Checking** 🧮
- **Memoization** 🧠
- **Efficient Math (√n Optimization)** 🚀
- **Array Mapping** 📑

---

## 🧪 Example Walkthrough

```js
Input:
[2, 3, 4, 5, 9]

Steps:
- 2 => Prime
- 3 => Prime
- 4 => Not prime (2 * 2 = 4)
- 5 => Prime
- 9 => Not prime (3 * 3 = 9)

Output:
[true, true, false, true, false]
```

---

## 🏷️ Tags

`#PrimeCheck` `#Memoization` `#MathOptimization` `#DynamicProgramming` `#JavaScript`

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

