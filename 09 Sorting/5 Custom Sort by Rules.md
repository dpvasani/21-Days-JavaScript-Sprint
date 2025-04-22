# 🔠 Custom Sort by Rules

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 12)  
> **Category:** String Sorting / Custom Comparator

---

## 🧩 Problem Statement

You are given a list of words and a custom alphabet order. Sort the words according to this custom order, similar to how an alien dictionary would sort words.

---

## 📥 Input Format

```js
[
  ["word", "words", "another", "example"],
  "zyxwvutsrqponmlkjihgfedcba"
]
```

---

## 📤 Output Format

Return the sorted array of words according to the custom alphabet order.

```js
["word", "words", "another", "example"]
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const [words, order] = input;

  // Create a mapping of each character to its index in the custom order
  const orderMap = {};
  for (let i = 0; i < order.length; i++) {
    orderMap[order[i]] = i;
  }

  // Custom comparison function to compare two words based on the custom order
  function compareWords(word1, word2) {
    const minLength = Math.min(word1.length, word2.length);

    for (let i = 0; i < minLength; i++) {
      const char1 = word1[i];
      const char2 = word2[i];

      if (orderMap[char1] !== orderMap[char2]) {
        return orderMap[char1] - orderMap[char2];  // Sort by order of characters
      }
    }

    return word1.length - word2.length; // If the words are equal up to the min length, sort by length
  }

  return words.sort(compareWords);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const [words, order] = input;

  // Create a mapping of each character to its index in the custom order
  const orderMap = {};
  for (let i = 0; i < order.length; i++) {
    orderMap[order[i]] = i;
  }

  // Custom comparison function to compare two words based on the custom order
  function compareWords(word1, word2) {
    const minLength = Math.min(word1.length, word2.length);

    for (let i = 0; i < minLength; i++) {
      const char1 = word1[i];
      const char2 = word2[i];

      if (orderMap[char1] !== orderMap[char2]) {
        return orderMap[char1] - orderMap[char2];  // Sort by order of characters
      }
    }

    return word1.length - word2.length; // If the words are equal up to the min length, sort by length
  }

  return words.sort(compareWords);
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

- Custom sorting based on character mapping
- Comparing words using a custom alphabet order
- Handling word length differences when characters are the same

---

## 🧪 Example

```js
Input:
[
  ["word", "words", "another", "example"],
  "zyxwvutsrqponmlkjihgfedcba"
]

Output:
["word", "words", "another", "example"]
```

---

## 🏷️ Tags

`#JavaScript` `#StringSorting` `#CustomComparator` `#Hard` `#D12`

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