# 🔍 Detect the Prefix (`myStartsWith`)

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 11)  
> **Category:** String Polyfill / Prototype

---

## 🧩 Problem Statement

Implement a polyfill called `myStartsWith` that mimics the behavior of `String.prototype.startsWith`.

---

## 📥 Input Format

```js
{
  str: "hello world",
  substr: "hello"
}
```

---

## 📤 Output Format

Return `true` if `str` starts with `substr`, else `false`.

---

## ✅ JavaScript Polyfill Solution

```js
String.prototype.myStartsWith = function(substr) {
  if (typeof substr !== 'string') return false;
  if (substr.length > this.length) return false;

  for (let i = 0; i < substr.length; i++) {
    if (this[i] !== substr[i]) {
      return false;
    }
  }

  return true;
};
```

---

## 📜 Full Code with Input Handler

```js
String.prototype.myStartsWith = function(substr) {
  if (typeof substr !== 'string') return false;
  if (substr.length > this.length) return false;

  for (let i = 0; i < substr.length; i++) {
    if (this[i] !== substr[i]) {
      return false;
    }
  }

  return true;
};

// Please don't touch the code below
function solve(input) {
  const { str, substr } = input;
  return str.myStartsWith(substr);
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

- Polyfilling built-in methods
- String indexing and comparison
- Type safety and boundary checks

---

## 🧪 Example

```js
Input:
{
  "str": "JavaScript",
  "substr": "Java"
}

Output:
true
```

---

## 🏷️ Tags

`#JavaScript` `#Polyfill` `#Prototype` `#StringMethods` `#Easy` `#D11`

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