# ✂️ Trim the Text (`myTrim`)

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 11)  
> **Category:** String Polyfill / Whitespace Handling

---

## 🧩 Problem Statement

In a text cleaner tool, Juno needs a custom trim function for removing leading and trailing whitespaces.  
Implement a polyfill called `myTrim` that mimics the behavior of `String.prototype.trim`.

---

## 📥 Input Format

```js
{
  str: "   Hello JavaScript!   "
}
```

---

## 📤 Output Format

Return a new string with leading and trailing whitespace removed.

---

## ✅ JavaScript Polyfill Solution

```js
String.prototype.myTrim = function () {
  let start = 0;
  let end = this.length - 1;

  while (start <= end && this[start] === ' ') {
    start++;
  }

  while (end >= start && this[end] === ' ') {
    end--;
  }

  return this.slice(start, end + 1);
};
```

---

## 📜 Full Code with Input Handler

```js
String.prototype.myTrim = function () {
  let start = 0;
  let end = this.length - 1;

  while (start <= end && this[start] === ' ') {
    start++;
  }

  while (end >= start && this[end] === ' ') {
    end--;
  }

  return this.slice(start, end + 1);
};

// Please don't touch the code below
function solve(input) {
  const { str } = input;
  return str.myTrim();
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

- String slicing
- Looping for space detection
- Polyfill logic for native methods

---

## 🧪 Example

```js
Input:
{
  "str": "   Polyfill Challenge!   "
}

Output:
"Polyfill Challenge!"
```

---

## 🏷️ Tags

`#JavaScript` `#Polyfill` `#Prototype` `#Trim` `#Medium` `#D11` `#StringMethods`

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