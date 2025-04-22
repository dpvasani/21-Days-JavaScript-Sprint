# 🔑 Wildcard Pattern Matching

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 13)  
> **Category:** Pattern Matching

---

## 🧩 Problem Statement

You are working on a file matching utility for a terminal command, similar to how glob patterns work in Unix/Linux systems. Your task is to implement a simplified pattern matching function that supports:

- `*` — Matches zero or more characters (any characters).
- `?` — Matches exactly one character (any character).
- All other characters must match exactly.

Given:
- A string representing the actual value (like a file name).
- A pattern string that may contain lowercase letters, `*`, and `?`.

Return `true` if the pattern matches the entire text, otherwise return `false`.

**Rules:**
- The match must cover the entire text (not just a substring).
- You must handle multiple `*` and `?` symbols.
- Only lowercase letters, `*`, and `?` are valid characters in the pattern.

---

## 📥 Input Format

```js
{
  "text": "abcdef",
  "pattern": "a*c"
}
```

---

## 📤 Output Format

Return `true` if the pattern matches the entire text, otherwise return `false`.

```js
true
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { text, pattern } = input;
  
  function match(text, pattern) {
    let dp = Array.from({ length: text.length + 1 }, () => Array(pattern.length + 1).fill(false));
    
    dp[0][0] = true;

    for (let j = 1; j <= pattern.length; j++) {
      if (pattern[j - 1] === '*') {
        dp[0][j] = dp[0][j - 1];
      }
    }

    for (let i = 1; i <= text.length; i++) {
      for (let j = 1; j <= pattern.length; j++) {
        if (pattern[j - 1] === text[i - 1] || pattern[j - 1] === '?') {
          dp[i][j] = dp[i - 1][j - 1];
        } else if (pattern[j - 1] === '*') {
          dp[i][j] = dp[i - 1][j] || dp[i][j - 1];
        }
      }
    }

    return dp[text.length][pattern.length];
  }
  
  return match(text, pattern);
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { text, pattern } = input;
  
  function match(text, pattern) {
    let dp = Array.from({ length: text.length + 1 }, () => Array(pattern.length + 1).fill(false));
    
    dp[0][0] = true;

    for (let j = 1; j <= pattern.length; j++) {
      if (pattern[j - 1] === '*') {
        dp[0][j] = dp[0][j - 1];
      }
    }

    for (let i = 1; i <= text.length; i++) {
      for (let j = 1; j <= pattern.length; j++) {
        if (pattern[j - 1] === text[i - 1] || pattern[j - 1] === '?') {
          dp[i][j] = dp[i - 1][j - 1];
        } else if (pattern[j - 1] === '*') {
          dp[i][j] = dp[i - 1][j] || dp[i][j - 1];
        }
      }
    }

    return dp[text.length][pattern.length];
  }
  
  return match(text, pattern);
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

- **Dynamic Programming (DP):** A 2D DP table is used to keep track of whether the pattern matches the substring of the text up to each point.
- **Pattern Matching:**
  - `*` matches zero or more characters.
  - `?` matches exactly one character.
  - Exact matches are checked directly.

---

## 🧪 Example

```js
Input:
{
  "text": "abcdef",
  "pattern": "a*c"
}

Output:
true
```

---

## 🏷️ Tags

`#JavaScript` `#PatternMatching` `#Wildcard` `#DynamicProgramming` `#Hard`

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