# 🔑 Count Word Frequency

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 14)  
> **Category:** Map, Object Manipulation

---

## 🧩 Problem Statement

You are given a list of lowercase words.  
Return an object where:
- The keys are the words.
- The values are their respective **frequencies**.  
You must use a **Map** to help build the frequency count.

---

## 📥 Input Format

```js
[string[]]
```

An array of lowercase strings (words).

Example:
```js
["apple", "banana", "apple", "orange", "banana", "apple"]
```

---

## 📤 Output Format

```js
{ [word: string]: number }
```

An object where each word is a key and its value is the frequency count.

Example:
```js
{
  "apple": 3,
  "banana": 2,
  "orange": 1
}
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const wordMap = new Map();

  for (const word of input) {
    wordMap.set(word, (wordMap.get(word) || 0) + 1);
  }

  const result = {};
  for (const [word, count] of wordMap) {
    result[word] = count;
  }

  return result;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const wordMap = new Map();

  for (const word of input) {
    wordMap.set(word, (wordMap.get(word) || 0) + 1);
  }

  const result = {};
  for (const [word, count] of wordMap) {
    result[word] = count;
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

- **Map:** Used for efficient key-value frequency counting.
- **Object Conversion:** Converting a `Map` back into a plain object for the final output.
- **Handling Counts:** Using `(wordMap.get(word) || 0) + 1` to handle new and existing words.

---

## 🧪 Example

```js
Input:
["apple", "banana", "apple", "orange", "banana", "apple"]

Output:
{
  "apple": 3,
  "banana": 2,
  "orange": 1
}
```

---

## 🏷️ Tags

`#JavaScript` `#Map` `#FrequencyCount` `#ObjectManipulation` `#Easy`

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

