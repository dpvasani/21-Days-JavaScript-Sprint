# 🍎 Fruit Basket Count

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint  
> **Category:** Data Iteration, Arrays, Object Manipulation

---

## 📝 Problem Statement

You are given an array containing names of fruits. Your task is to **return an object** where the keys are fruit names and the values are the **number of times each fruit appears** in the array.

---

## 📥 Input Format

- A single array of strings, where each string represents a fruit name.

### Example Input

```json
["apple", "banana", "apple", "orange"]
```

---

## 📤 Output Format

- An object with each fruit as the key and the number of occurrences as the value.

### Example Output

```json
{
  "apple": 2,
  "banana": 1,
  "orange": 1
}
```

---

## 🔒 Constraints

- `1 <= input.length <= 1000`
- Each fruit name is a lowercase string.
- The array may contain duplicates.

---

## 💡 Hints

- Use an object to store counts.
- Iterate through the array and update the count accordingly.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const fruitCount = {};

  for (let fruit of input) {
    fruitCount[fruit] = (fruitCount[fruit] || 0) + 1;
  }

  return fruitCount;
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

`#JavaScript` `#Array` `#Object` `#Counting` `#DataIteration`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
