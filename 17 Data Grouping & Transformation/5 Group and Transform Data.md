# 📊 Group and Transform Data

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 20)  
> **Category:** Data Transformation | Object Grouping | Sorting

---

## 🧩 Problem Statement

You're given an array of **transactions**, where each transaction has:

- `userId` (number)
- `amount` (number)
- `timestamp` (string in ISO format)

### 🎯 Goal:

Group all transactions **by `userId`**, and for each user:

- Return the **total amount spent**
- Return the **earliest transaction timestamp**

📦 The final output should be an array of objects like this:

```js
[
  { userId: 1, totalAmount: 450, earliestTransaction: "2024-04-01T10:00:00Z" },
  ...
]
```

🔢 Sort the final array by `userId` in **ascending order**.

---

## 📥 Input Format

An array of transaction objects:

```json
[
  { "userId": 1, "amount": 200, "timestamp": "2024-04-01T10:00:00Z" },
  { "userId": 2, "amount": 300, "timestamp": "2024-04-01T12:00:00Z" },
  { "userId": 1, "amount": 250, "timestamp": "2024-03-30T09:00:00Z" }
]
```

---

## 📤 Output Format

A sorted array of user summary objects:

```json
[
  { "userId": 1, "totalAmount": 450, "earliestTransaction": "2024-03-30T09:00:00Z" },
  { "userId": 2, "totalAmount": 300, "earliestTransaction": "2024-04-01T12:00:00Z" }
]
```

---

## 🧪 Example

### Input:

```json
[
  { "userId": 10, "amount": 100, "timestamp": "2024-01-10T08:00:00Z" },
  { "userId": 10, "amount": 150, "timestamp": "2024-01-05T07:30:00Z" },
  { "userId": 5, "amount": 80, "timestamp": "2024-01-08T09:00:00Z" }
]
```

### Output:

```json
[
  { "userId": 5, "totalAmount": 80, "earliestTransaction": "2024-01-08T09:00:00Z" },
  { "userId": 10, "totalAmount": 250, "earliestTransaction": "2024-01-05T07:30:00Z" }
]
```

---

## ✅ JavaScript Solution

### Approach:

- Use an object to group transactions by `userId`.
- Sum the `amount` for each user.
- Compare and store the **earliest timestamp**.
- Convert grouped object to an array.
- Sort the array by `userId`.

---

### JavaScript Code:

```js
function solve(input) {
  const map = {};

  for (const txn of input) {
    const { userId, amount, timestamp } = txn;

    if (!map[userId]) {
      map[userId] = {
        userId,
        totalAmount: amount,
        earliestTransaction: timestamp,
      };
    } else {
      map[userId].totalAmount += amount;
      if (timestamp < map[userId].earliestTransaction) {
        map[userId].earliestTransaction = timestamp;
      }
    }
  }

  return Object.values(map).sort((a, b) => a.userId - b.userId);
}
```

---

## 🧾 Full Code with Input Handler

```js
function solve(input) {
  const map = {};

  for (const txn of input) {
    const { userId, amount, timestamp } = txn;

    if (!map[userId]) {
      map[userId] = {
        userId,
        totalAmount: amount,
        earliestTransaction: timestamp,
      };
    } else {
      map[userId].totalAmount += amount;
      if (timestamp < map[userId].earliestTransaction) {
        map[userId].earliestTransaction = timestamp;
      }
    }
  }

  return Object.values(map).sort((a, b) => a.userId - b.userId);
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

- **Object grouping**
- **Date comparison using string (ISO format)**
- **Sorting objects**
- **Object to array transformation**

---

## 🏷️ Tags

`#ObjectGrouping` `#ISODateComparison` `#DataTransformation` `#Sorting` `#JavaScriptAdvanced`

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

