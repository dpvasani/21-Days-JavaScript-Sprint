# 🔢 Frequency Sort

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 12)  
> **Category:** Array Sorting / Frequency Counting

---

## 🧩 Problem Statement

Given an array of integers, sort them by frequency in descending order.  
If the frequencies are the same, sort by the value in ascending order.

---

## 📥 Input Format

```js
[4, 4, 6, 7, 8, 7, 9, 7]
```

---

## 📤 Output Format

Return the array sorted by the frequency of elements in descending order, and by value in ascending order when frequencies are the same.

```js
[7, 7, 7, 4, 4, 6, 8, 9]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const freqMap = {};
  input.forEach(num => {
    freqMap[num] = (freqMap[num] || 0) + 1;
  });

  return input.sort((a, b) => {
    const freqDiff = freqMap[b] - freqMap[a];
    if (freqDiff === 0) {
      return a - b;
    }
    return freqDiff;
  });
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const freqMap = {};
  input.forEach(num => {
    freqMap[num] = (freqMap[num] || 0) + 1;
  });

  return input.sort((a, b) => {
    const freqDiff = freqMap[b] - freqMap[a];
    if (freqDiff === 0) {
      return a - b;
    }
    return freqDiff;
  });
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- Frequency counting with hash maps
- Sorting with custom comparator functions
- Array sorting based on multiple criteria

---

## 🧪 Example

```js
Input:
[4, 6, 7, 7, 8, 9, 7, 4]

Output:
[7, 7, 7, 4, 4, 6, 8, 9]
```

---

## 🏷️ Tags

`#JavaScript` `#ArraySorting` `#FrequencyCounting` `#Medium` `#D12`

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