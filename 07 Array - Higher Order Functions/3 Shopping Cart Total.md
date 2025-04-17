# 🛒 Shopping Cart Total

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Arrays / Objects / Reduce

---

## Problem Statement

You're running a small online store. Each item in a customer's shopping cart is represented as an object:

```js
{ price: number, quantity: number }
```

Write a function `solve(input)` that calculates the **total cost** of all items in the cart.

> 💡 Multiply each item's price by its quantity and sum them all up.

---

## Input Format

An array of objects, where each object has:
- `price`: a number (cost of one unit)
- `quantity`: a number (how many units the customer wants)

### Example:

```json
Input: [
  { "price": 100, "quantity": 2 },
  { "price": 200, "quantity": 1 },
  { "price": 50, "quantity": 4 }
]
Output: 500
```

---

## Output Format

A single integer — the total price.

---

## JavaScript Solution

```js
function solve(input) {
  return input.reduce((total, item) => {
    return total + item.price * item.quantity;
  }, 0);
}
```

---

## Code with Test Handler

```js
// Your task is to implement this function
function solve(input) {
  return input.reduce((total, item) => {
    return total + item.price * item.quantity;
  }, 0);
}

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Explanation

- `reduce()` starts with `0` and adds `price * quantity` for each item.
- Great use case for calculating totals in invoices or carts.

---

## 🏷️ Tags

`#JavaScript` `#Reduce` `#ShoppingCart` `#Objects` `#Arrays` `#Interview`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me!  
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐙 [github.com/dpvasani](https://github.com/dpvasani)  
💼 [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
📢 [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---
