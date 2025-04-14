# 🔁 Reverse String Using Loop

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 2)  
> **Category:** Strings, Loops

---

## 📝 Problem Statement

You are given a string.  
Return the **reversed string using a loop**.

❗️**Do not use** built-in methods like `.reverse()` or `.split().reverse().join()`.

---

## 📥 Input Format

A string input.

### Example Input

```json
"hello"
```

---

## 📤 Output Format

A string, reversed.

### Example Output

```json
"olleh"
```

---

## 🔒 Constraints

- Input string can contain lowercase/uppercase letters, spaces, digits, and symbols.
- Length of the string ≤ `10^4`.

---

## 💡 Hints

- Use a `for` loop to iterate from the end of the string to the beginning.
- Concatenate each character to build the reversed string.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let reversed = "";
  for (let i = input.length - 1; i >= 0; i--) {
    reversed += input[i];
  }
  return reversed;
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

## 🏷️ Tags

`#JavaScript` `#StringManipulation` `#ForLoop` `#ReverseString`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
