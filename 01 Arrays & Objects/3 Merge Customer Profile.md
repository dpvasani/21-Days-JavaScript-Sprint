# 🧾 Merge Customer Profile

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint  
> **Category:** Data Iteration, Array/Object Merging, Map

---

## 📝 Problem Statement

You are given **two arrays** of customer objects. Each object has the following structure:

```js
{ id: number, name: string }
```

Your task is to **merge the two arrays by `id`**, ensuring that:

- If a customer appears in both arrays (with the same `id`), **the version from the second array should be used**.
- If a customer appears in only one array, include them as-is.

Return the merged array of customer profiles.

---

## 📥 Input Format

An array with two arrays inside:

```json
[
  [ { "id": 1, "name": "Alice" }, { "id": 2, "name": "Bob" } ],
  [ { "id": 2, "name": "Bobby" }, { "id": 3, "name": "Charlie" } ]
]
```

---

## 📤 Output Format

An array of merged customer profiles, **order is not important**.

### Example Output

```json
[
  { "id": 1, "name": "Alice" },
  { "id": 2, "name": "Bobby" },
  { "id": 3, "name": "Charlie" }
]
```

---

## 🔒 Constraints

- `1 <= total number of objects <= 1000`
- All `id`s are positive integers.
- The second array may overwrite entries from the first.

---

## 💡 Hints

- Use a `Map` or an object with `id` as the key to track latest data.
- Iterate both arrays and update the map.
- Convert the map values back to an array for the final output.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const [arr1, arr2] = input;
  const customerMap = new Map();

  // Add all customers from the first array
  for (const customer of arr1) {
    customerMap.set(customer.id, customer);
  }

  // Overwrite or add from the second array
  for (const customer of arr2) {
    customerMap.set(customer.id, customer);
  }

  return Array.from(customerMap.values());
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

`#JavaScript` `#Merge` `#Array` `#Object` `#Map` `#DataIteration`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
