# 📝 Online Store with Discount and Stock Management

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 5)  
> **Category:** Prototypes

---

## Problem Statement

You are developing an online store system where each product has the following properties:
- `name`: The name of the product (e.g., `"Laptop"`).
- `price`: The price of the product (a positive integer).
- `stock`: The available stock (a non-negative integer).

Your task is to implement the following methods:
1. **applyDiscount(percent)**  
   Reduces the price of the product by the given percentage. The final price should be rounded to the nearest integer.
   
   Example: If a product costs $1000 and a 10% discount is applied, the new price should be $900.
   
2. **purchase(quantity)**  
   - If the requested quantity is available in stock, reduce the stock accordingly.
   - If not enough stock is available, return `"Not enough stock"`.

---

## Input Format

The input consists of a `product` object with `name`, `price`, and `stock`, along with an `action` object which can either be a `discount` or `purchase` type.

### Example Input

```json
{
  "product": {
    "name": "Laptop",
    "price": 1000,
    "stock": 10
  },
  "action": {
    "type": "discount",
    "percent": 10
  }
}
```

---

## Output Format

For the `discount` action, the output should be the updated price and stock of the product.  
For the `purchase` action, the output should be the updated stock or a message `"Not enough stock"` if the purchase quantity exceeds available stock.

### Example Output

```json
[900, 10]
```

---

## JavaScript Solution

```js
function Product(name, price, stock) {
  // Initialize name, price, and stock properties
  this.name = name;
  this.price = price;
  this.stock = stock;
}

// Define applyDiscount method on Product's prototype
Product.prototype.applyDiscount = function(percent) {
  this.price = Math.round(this.price * (1 - percent / 100));
};

// Define purchase method on Product's prototype
Product.prototype.purchase = function(quantity) {
  if (this.stock >= quantity) {
    this.stock -= quantity;
    return this.stock;
  } else {
    return "Not enough stock";
  }
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { product, action } = JSON.parse(input);
  const storeItem = new Product(product.name, product.price, product.stock);

  if (action.type === "discount") {
    storeItem.applyDiscount(action.percent);
  } else if (action.type === "purchase") {
    process.stdout.write(JSON.stringify(storeItem.purchase(action.quantity)));
    return;
  }

  process.stdout.write(JSON.stringify([storeItem.price, storeItem.stock]));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#Discount` `#StockManagement` `#OnlineStore`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
