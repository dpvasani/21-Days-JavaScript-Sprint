
# 🏷️ Odd or Even Badge

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 4)  
> **Category:** Basic Logic

---

## 📝 Problem Statement

A security system assigns "Odd" or "Even" badges to employees based on the number of letters in their names:

- If the length of the name is even, return "Even".
- If the length of the name is odd, return "Odd".

---

## 📥 Input Format

- A single string representing the name of the employee.

### Example Input

```json
"John"
```

---

## 📤 Output Format

- A string: "Odd" if the name length is odd, and "Even" if it’s even.

### Example Output

```json
"Odd"
```

---

## 🔒 Constraints

- The length of the name will be a positive integer, and the name will consist of alphabetical characters.

---

## 💡 Hints

- You can easily check if a number is even or odd by using the modulus operator (`%`).
  
---

## ✅ JavaScript Solution

```js
function solve(name) {
  return name.length % 2 === 0 ? "Even" : "Odd";
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const name = JSON.parse(input);
  const result = solve(name);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#String` `#Logic`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
