# 🧮 Transform Array to Object with Sums

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 20)  
> **Category:** Object Aggregation | Array Manipulation | Data Transformation

---

## 🧩 Problem Statement

You're provided with an **array of objects**, where each object contains the following properties:

- `product`: a string representing the product name.
- `price`: a number representing the product’s price.

Your task is to **transform** this array into an **object** where:

- The **keys** are unique product names.
- The **values** are the **sum of prices** of that product.
- If the same product appears multiple times, **sum their prices**.

---

## 📥 Input Format

An array of objects with the structure:

```json
[
  { "product": "apple", "price": 30 },
  { "product": "banana", "price": 10 },
  { "product": "apple", "price": 20 }
]
```

---

## 📤 Output Format

An object where keys are product names, and values are the total summed prices:

```json
{
  "apple": 50,
  "banana": 10
}
```

---

## 🧪 Example

### Input:

```json
[
  { "product": "pen", "price": 5 },
  { "product": "notebook", "price": 15 },
  { "product": "pen", "price": 3 },
  { "product": "notebook", "price": 10 }
]
```

### Output:

```json
{
  "pen": 8,
  "notebook": 25
}
```

---

## ✅ JavaScript Solution

### Approach:

- Initialize an empty object `result`.
- Loop through each item in the input array.
- For each product:
  - Check if the product already exists in the result object.
  - If yes, add the current price to the existing value.
  - If not, initialize it with the current price.

---

### JavaScript Code:

```js
function solve(input) {
  const result = {};

  for (const item of input) {
    const { product, price } = item;

    if (!result[product]) {
      result[product] = 0;
    }

    result[product] += price;
  }

  return result;
}
```

---

## 🧾 Full Code with Input Handler

```js
function solve(input) {
  const result = {};

  for (const item of input) {
    const { product, price } = item;

    if (!result[product]) {
      result[product] = 0;
    }

    result[product] += price;
  }

  return result;
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

- **Aggregation by key**: Group and sum based on a shared property.
- **Dynamic object keys**: Constructing keys at runtime.
- **Efficient accumulation**: Using conditional initialization and addition.

---

## 🏷️ Tags

`#ObjectAggregation` `#ArrayTransformation` `#SumValues` `#JavaScriptObjects` `#MediumLevel`

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
