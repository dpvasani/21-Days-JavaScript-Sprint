# 🔍 Find the First (myFind)

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 10)  
> **Category:** Polyfill / Array.prototype / Find

---

## 🧩 Problem Statement

Arjun needs to identify the **first faulty sensor** from a sequence. But the system doesn't support `Array.prototype.find`.  
Implement a polyfill called `myFind` that behaves **exactly like the native `.find()`**.

---

## 📥 Input Format

An object with:
- `array`: Array of elements to search through
- `callbackStr`: A stringified version of a callback function (e.g. `"(val) => val > 5"`)

---

## 📤 Output Format

The **first element** that satisfies the condition. If no match, return `undefined`.

---

## 🧪 Example

```json
Input:
{
  "array": [1, 3, 7, 4, 9],
  "callbackStr": "(val) => val > 5"
}

Output:
7
```

---

## ✅ JavaScript Solution

```js
Array.prototype.myFind = function(callback) {
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      return this[i];
    }
  }
  return undefined;
};
```

---

## 📜 Full Code with Input Handler

```js
Array.prototype.myFind = function(callback) {
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      return this[i];
    }
  }
  return undefined;
};

// Please don't touch the code below
function solve(input) {
  const { array, callbackStr } = input;
  const callback = eval(callbackStr);
  return array.myFind(callback);
}

const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  console.log(result);
});
```

---

## 🧠 Explanation

- Loops through the array.
- Applies the `callback` function to each element.
- Returns the **first element** for which the callback returns `true`.
- Returns `undefined` if **no match** is found.

---

## 🏷️ Tags

`#JavaScript` `#ArrayMethods` `#Polyfill` `#Find` `#Medium` `#D10`

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