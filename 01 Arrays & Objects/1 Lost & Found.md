# 🧠 Lost & Found - Unique Item Names

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint  
> **Category:** Data Iteration, Array, Object Manipulation

---

## 📝 Problem Statement

A lost-and-found department stores each report as an object in the form:

```js
{ name: string, item: string }
```

Given an array of such objects, return a list of all **unique item names** that have been reported, **sorted alphabetically**.

---

## 📥 Input Format

- An array of objects, where each object contains:
  - `name`: The name of the person who reported the item.
  - `item`: The item reported.

### Example Input

```json
[
  { "name": "Avi", "item": "Phone" },
  { "name": "Bea", "item": "Wallet" },
  { "name": "Avi", "item": "Phone" }
]
```

---

## 📤 Output Format

- An array of unique item names sorted in **alphabetical** order.

### Example Output

```json
["Phone", "Wallet"]
```

---

## 🔒 Constraints

- `1 <= input.length <= 1000`
- `item` will always be a string.
- Items may be reported multiple times by the same or different people.

---

## 💡 Hints

- Use a `Set` to collect unique values.
- Use `.sort()` to sort strings alphabetically.

---

## ✅ JavaScript Solution

```js
function solve(input) {
  // Collect all items from the input objects
  let items = [];
  for (let i = 0; i < input.length; i++) {
    items.push(input[i].item);
  }

  // Create a Set to remove duplicates, then sort alphabetically
  let uniqueItems = [...new Set(items)].sort();
  return uniqueItems;
}

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Array` `#Set` `#Sorting` `#Objects`

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