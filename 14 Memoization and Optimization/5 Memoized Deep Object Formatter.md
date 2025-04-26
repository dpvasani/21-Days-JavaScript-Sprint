# 🛠️ Memoized Deep Object Formatter

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 17)  
> **Category:** Memoization | Objects | String Manipulation

---

## 🧩 Problem Statement

You are building a **data formatting service**.  
Given an **array of user objects**, for each object:

- Create a **summary string** from the fields: `"name, age from city"`.
- Use **memoization** based on a **stringified version** of the object to avoid recomputing if the same user data appears again.

---

## 📥 Input Format

```json
[
  { "name": "Alice", "age": 28, "city": "NY" },
  { "name": "Bob", "age": 32, "city": "LA" }
]
```

---

## 📤 Output Format

```json
[
  "Alice, 28 from NY",
  "Bob, 32 from LA"
]
```

---

## 📌 Important Notes

- **Memoize** results by using `JSON.stringify(user)` as the key.
- Ensure **identical user objects** are **formatted only once**.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const memo = {};

  function formatter(user) {
    const key = JSON.stringify(user);
    if (key in memo) return memo[key];
    const formatted = `${user.name}, ${user.age} from ${user.city}`;
    memo[key] = formatted;
    return formatted;
  }

  return input.map(formatter);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const memo = {};

  function formatter(user) {
    const key = JSON.stringify(user);
    if (key in memo) return memo[key];
    const formatted = `${user.name}, ${user.age} from ${user.city}`;
    memo[key] = formatted;
    return formatted;
  }

  return input.map(formatter);
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

- **Memoization** for Deep Objects 🧠
- **JSON.stringify for Object Keys** 🔑
- **Efficient String Formatting** ✨
- **Mapping Arrays** 📑

---

## 🧪 Example Walkthrough

```js
Input:
[
  { "name": "Alice", "age": 28, "city": "NY" },
  { "name": "Bob", "age": 32, "city": "LA" },
  { "name": "Alice", "age": 28, "city": "NY" } // repeated
]

Steps:
- Format "Alice, 28 from NY" and memoize it.
- Format "Bob, 32 from LA" and memoize it.
- See repeated Alice => fetch from memo.

Output:
[
  "Alice, 28 from NY",
  "Bob, 32 from LA",
  "Alice, 28 from NY"
]
```

---

## 🏷️ Tags

`#Memoization` `#ObjectHandling` `#StringFormatting` `#DeepEquality` `#JSONStringify` `#JavaScript`

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

