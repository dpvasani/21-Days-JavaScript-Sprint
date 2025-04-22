# 🔍 Custom `myIncludes` (`myIncludes`)

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 11)  
> **Category:** String Polyfill / Prototype

---

## 🧩 Problem Statement

Leo's application checks if a keyword exists in system logs.  
Implement a polyfill called `myIncludes` that mimics the behavior of `String.prototype.includes`.

---

## 📥 Input Format

```js
{
  str: "the quick brown fox",
  substr: "quick"
}
```

---

## 📤 Output Format

Return `true` if `substr` exists anywhere in `str`, else `false`.

---

## ✅ JavaScript Polyfill Solution

```js
String.prototype.myIncludes = function(substr) {
  if (typeof substr !== 'string') return false;
  if (substr.length === 0) return true;

  for (let i = 0; i <= this.length - substr.length; i++) {
    let match = true;
    for (let j = 0; j < substr.length; j++) {
      if (this[i + j] !== substr[j]) {
        match = false;
        break;
      }
    }
    if (match) return true;
  }

  return false;
};
```

---

## 📜 Full Code with Input Handler

```js
String.prototype.myIncludes = function(substr) {
  if (typeof substr !== 'string') return false;
  if (substr.length === 0) return true;

  for (let i = 0; i <= this.length - substr.length; i++) {
    let match = true;
    for (let j = 0; j < substr.length; j++) {
      if (this[i + j] !== substr[j]) {
        match = false;
        break;
      }
    }
    if (match) return true;
  }

  return false;
};

// Please don't touch the code below
function solve(input) {
  const { str, substr } = input;
  return str.myIncludes(substr);
}

const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- Manual substring comparison
- Nested loops for pattern checking
- Polyfill logic for core string methods

---

## 🧪 Example

```js
Input:
{
  "str": "learning JavaScript polyfills",
  "substr": "Script"
}

Output:
true
```

---

## 🏷️ Tags

`#JavaScript` `#Polyfill` `#Prototype` `#StringMethods` `#Medium` `#D11`

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