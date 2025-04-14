# 📝 Shopping Cart with Total Calculation

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 5)  
> **Category:** Prototypes

---

## Problem Statement

Create a Shopping Cart system where items can be added with a price. Implement a method `getTotalPrice()` that calculates the total price of all items in the cart.

### Challenge:
- Implement a constructor function `ShoppingCart` that initializes an empty `items` array.
- Attach a method `addItem(price)` to the prototype to add items with a given price.
- Attach a method `getTotalPrice()` to the prototype to calculate the total price of the items in the cart.

---

## Input Format

The input contains a list of item prices.

### Example Input

```json
{
  "prices": [10, 20, 30]
}
```

---

## Output Format

The output should be the total price of all items in the cart.

### Example Output

```json
60
```

---

## JavaScript Solution

```js
function ShoppingCart() {
  // Initialize items property as an empty array
  this.items = [];
}

// Define addItem method on ShoppingCart's prototype
ShoppingCart.prototype.addItem = function(price) {
  this.items.push(price);
};

// Define getTotalPrice method on ShoppingCart's prototype
ShoppingCart.prototype.getTotalPrice = function() {
  // Calculate the sum of all item prices
  return this.items.reduce((total, price) => total + price, 0);
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { prices } = JSON.parse(input);
  const cart = new ShoppingCart();

  for (let price of prices) {
    cart.addItem(price);
  }

  process.stdout.write(JSON.stringify(cart.getTotalPrice()));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#ShoppingCart` `#TotalPrice` `#Methods`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
