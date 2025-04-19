# 🧹 Filter the Logs (myFilter)

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 10)  
> **Category:** Array Methods / Polyfills / Prototypes

---

## 🧩 Problem Statement

Anirudh is monitoring server logs and needs to filter specific entries. However, the JavaScript environment does **not support `Array.prototype.filter`**.

Your task is to **create a custom polyfill** named `myFilter` that behaves exactly like the native `filter()` function.

---

## 📥 Input Format

An object with:
- `array`: An array of items (e.g., numbers, strings, etc.)
- `callbackStr`: A string representing the filter condition callback (e.g., `"(x) => x > 10"`)

---

## 📤 Output Format

A filtered array containing elements for which the callback returned `true`.

---

## 🧪 Example

```json
Input:
{
  "array": [1, 12, 5, 18],
  "callbackStr": "(x) => x > 10"
}

Output:
[12, 18]
```

---

## ✅ JavaScript Solution

```js
Array.prototype.myFilter = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};
```

---

## 📜 Full Code with Input Handler

```js
Array.prototype.myFilter = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};

// Please don't touch the code below
function solve(input) {
  const { array, callbackStr } = input;
  const callback = eval(callbackStr);
  return array.myFilter(callback);
}

const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const result = solve(JSON.parse(input));
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Explanation

- Extends `Array.prototype` with a custom `myFilter` method.
- Iterates through the array using a loop.
- Applies the callback on each element.
- If the callback returns `true`, the element is added to the result array.
- Returns the filtered result array.

---

## 🏷️ Tags

`#JavaScript` `#Polyfill` `#ArrayMethods` `#Filter` `#Easy` `#D10`

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