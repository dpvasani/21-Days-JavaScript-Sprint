# 🧩 First Non-Repeating Character

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 3)  
> **Category:** String Manipulation

---

## 📝 Problem Statement

Given a string, return the **first non-repeating character**. If no such character exists, return `null`.

### Example:

- **Input:** `"abacabad"`
- **Output:** `"c"`

- **Input:** `"aabbcc"`
- **Output:** `null`

---

## 📥 Input Format

A string `input`.

### Example Input

```json
"abacabad"
```

---

## 📤 Output Format

The first non-repeating character, or `null` if no such character exists.

### Example Output

```json
"c"
```

---

## 🔒 Constraints

- The input string may contain letters, digits, symbols, and spaces.
- The length of the string: `1 <= str.length <= 1000`.

---

## 💡 Hints

- You can use a frequency map to count the occurrences of each character in the string.
- Iterate over the string again and return the first character that has a frequency of 1.
- If no such character exists, return `null`.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const freqMap = {};

  // Count the frequency of each character
  for (let char of input) {
    freqMap[char] = (freqMap[char] || 0) + 1;
  }

  // Find the first character that occurs only once
  for (let char of input) {
    if (freqMap[char] === 1) {
      return char;
    }
  }

  // If no non-repeating character exists, return null
  return null;
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

`#JavaScript` `#StringManipulation` `#NonRepeatingCharacter`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
