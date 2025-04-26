# ☕ Curry Cafe

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 16)  
> **Category:** Functions | Currying

---

## 🧩 Problem Statement

You are building a **digital ordering system** for a café.  
You need to create a **curried function** that:
- First accepts the **drink** (e.g., `"Latte"`),
- Then accepts the **size** (e.g., `"Large"`),
- Finally accepts the **customer's name** (e.g., `"Alice"`).

✅ The final function should return a formatted string:
```
"Order placed: <drink> - <size> for <name>"
```

---

## 📥 Input Format

An object with:
```js
{
  drink: "Latte",
  size: "Large",
  name: "Alice"
}
```

---

## 📤 Output Format

A string like:
```js
"Order placed: Latte - Large for Alice"
```

---

## 📌 Important Notes

- The function must be **curried** (i.e., returns a function at each step).
- Keep the order: **Drink → Size → Name**.

---

## ✅ JavaScript Solution

```js
function curryOrder(drink) {
  return function(size) {
    return function(name) {
      return `Order placed: ${drink} - ${size} for ${name}`;
    };
  };
}
```

---

## 📜 Full Code with Input Handler

```js
function curryOrder(drink) {
  return function(size) {
    return function(name) {
      return `Order placed: ${drink} - ${size} for ${name}`;
    };
  };
}

// Do not touch the code below
function solve(input) {
  const { drink, size, name } = input;
  const result = curryOrder(drink)(size)(name);
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

- **Currying Functions** 🎯
- **Closures** 📦
- **String Interpolation** 🔥
- **Function Chaining**

---

## 🧪 Example

```js
Input:
{ drink: "Mocha", size: "Medium", name: "John" }

Output:
"Order placed: Mocha - Medium for John"
```

---

## 🏷️ Tags

`#JavaScript` `#Functions` `#Currying` `#Closures`

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

