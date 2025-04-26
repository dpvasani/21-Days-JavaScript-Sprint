# 🔗 Compose Two

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 16)  
> **Category:** Functions | Function Composition

---

## 🧩 Problem Statement

You're building a **math function engine** where users can plug in two simple functions and a number.  
You need to create a `compose(f, g)` function that:

- Takes two functions `f` and `g` as input.
- Returns a new function that takes `x` as input.
- The returned function should:
  1. Apply `g(x)` first.
  2. Then apply `f(g(x))`.
  3. Return the final result.

✅ In short, it should compute:  
```js
f(g(x))
```

---

## 📥 Input Format

An object containing:
```js
{
  f: "x => x * 2",
  g: "x => x + 3",
  x: 5
}
```

---

## 📤 Output Format

A single number: the final result of applying `f(g(x))`.

---

## 📌 Important Notes

- `f` and `g` will be given as **stringified functions**.
- You must safely use `eval` to **convert strings into actual functions**.
- First apply **g**, then apply **f** to the result.
- Don't reverse the order! 🚫

---

## ✅ JavaScript Solution

```js
function compose(f, g) {
  return function(x) {
    return f(g(x));
  };
}
```

---

## 📜 Full Code with Input Handler

```js
function compose(f, g) {
  return function(x) {
    return f(g(x));
  };
}

// Do not touch the code below
function solve(input) {
  const { f, g, x } = input;
  const fFn = eval(f);
  const gFn = eval(g);
  const result = compose(fFn, gFn)(x);
  return result;
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

- **Function Composition** 🔁
- **Higher Order Functions** 🚀
- **Evaluating Strings to Functions** (`eval`)
- **Closures**

---

## 🧪 Example

```js
Input:
{
  f: "x => x * 2",
  g: "x => x + 3",
  x: 5
}

Steps:
g(5) = 5 + 3 = 8
f(8) = 8 * 2 = 16

Output:
16
```

---

## 🏷️ Tags

`#JavaScript` `#Functions` `#Compose` `#FunctionalProgramming`

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

