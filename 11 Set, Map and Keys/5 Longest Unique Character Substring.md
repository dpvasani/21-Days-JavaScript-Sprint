# 🔠 Longest Unique Character Substring

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 14)  
> **Category:** Sliding Window, Set, String

---

## 🧩 Problem Statement

You are given a string.  
Return the **length of the longest substring** without any **repeating characters**.

- You should use a `Set` to help keep track of unique characters.

---

## 📥 Input Format

```js
string
```

A single string containing lowercase (and possibly uppercase) letters.

Example:
```js
"abcabcbb"
```

---

## 📤 Output Format

```js
number
```

The length of the longest substring with all unique characters.

Example:
```js
3
```
(Substring is `"abc"`)

---

## ✅ JavaScript Solution

```js
function solve(input) {
  let set = new Set();
  let left = 0, maxLength = 0;

  for (let right = 0; right < input.length; right++) {
    while (set.has(input[right])) {
      set.delete(input[left]);
      left++;
    }
    set.add(input[right]);
    maxLength = Math.max(maxLength, right - left + 1);
  }

  return maxLength;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  let set = new Set();
  let left = 0, maxLength = 0;

  for (let right = 0; right < input.length; right++) {
    while (set.has(input[right])) {
      set.delete(input[left]);
      left++;
    }
    set.add(input[right]);
    maxLength = Math.max(maxLength, right - left + 1);
  }

  return maxLength;
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

- **Sliding Window Technique:** Dynamically adjusting window size to maintain unique characters.
- **Set Usage:** Checking and managing unique characters efficiently.
- **Dynamic Pointers:** `left` and `right` pointers to control current substring.

---

## 🧪 Example

```js
Input:
"abcabcbb"

Output:
3
(Explanation: The substring "abc" is the longest with all unique characters.)

Input:
"bbbbb"

Output:
1
(Explanation: The substring "b" is the longest.)

Input:
"pwwkew"

Output:
3
(Explanation: The substring "wke" is the longest.)
```

---

## 🏷️ Tags

`#JavaScript` `#SlidingWindow` `#Sets` `#StringHandling` `#Hard`

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

