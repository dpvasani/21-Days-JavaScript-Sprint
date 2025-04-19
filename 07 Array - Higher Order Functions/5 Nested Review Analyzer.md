# 🧩 Nested Review Analyzer

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Objects / Nested Data / Sorting / Aggregation

---

## Problem Statement

You manage a collection of product reviews. Each review includes:

```js
{
  product: string,
  ratings: {
    quality: number,
    delivery: number,
    packaging: number
  }
}
```

Write a function `solve(input)` that returns a new array of objects, each with:

```js
{ product: string, averageRating: number }
```

The result should be **sorted in descending order** of averageRating.

> 💡 This problem requires computing averages from nested objects and sorting the result.

---

## Input Format

An array of review objects:
- `product`: a string — name of the product.
- `ratings`: an object with `quality`, `delivery`, and `packaging` scores (all numbers).

---

## Output Format

An array of objects with:
- `product`: string
- `averageRating`: number (rounded to two decimal places if needed)

---

### Example:

```json
Input: [
  { "product": "Phone", "ratings": { "quality": 8, "delivery": 9, "packaging": 7 } },
  { "product": "Laptop", "ratings": { "quality": 9, "delivery": 9, "packaging": 9 } },
  { "product": "Tablet", "ratings": { "quality": 7, "delivery": 6, "packaging": 8 } }
]

Output: [
  { "product": "Laptop", "averageRating": 9 },
  { "product": "Phone", "averageRating": 8 },
  { "product": "Tablet", "averageRating": 7 }
]
```

---

## JavaScript Solution

```js
function solve(input) {
  return input
    .map(review => {
      const ratings = Object.values(review.ratings);
      const avg = ratings.reduce((sum, r) => sum + r, 0) / ratings.length;
      return {
        product: review.product,
        averageRating: Math.round(avg)
      };
    })
    .sort((a, b) => b.averageRating - a.averageRating);
}
```

---

## Code with Test Handler

```js
function solve(input) {
  return input
    .map(review => {
      const ratings = Object.values(review.ratings);
      const avg = ratings.reduce((sum, r) => sum + r, 0) / ratings.length;
      return {
        product: review.product,
        averageRating: Math.round(avg)
      };
    })
    .sort((a, b) => b.averageRating - a.averageRating);
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

- `Object.values()` extracts the numeric ratings from the nested object.
- `reduce()` calculates the sum, and dividing by the number of categories gives the average.
- The result is sorted using `.sort()` in descending order of `averageRating`.

---

## 🏷️ Tags

`#JavaScript` `#Objects` `#NestedData` `#Sorting` `#Reduce` `#Averages` `#Hard`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🎓 **Credly:** [credly.com/users/dpvasani57](https://www.credly.com/users/dpvasani57/)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)  

---