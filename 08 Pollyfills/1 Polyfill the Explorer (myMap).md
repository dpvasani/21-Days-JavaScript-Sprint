# ⚓ Polyfill the Explorer (myMap)

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 10)  
> **Category:** Array Methods / Polyfills / Prototypes

---

## 🧩 Problem Statement

Rina is debugging a ship control system that runs on an **outdated JavaScript engine** which **does not support** the built-in `Array.prototype.map` method.

Create a **custom polyfill** called `myMap` on the `Array.prototype` that mimics the behavior of the **native `map()`** function.

---

## 📥 Input Format

An object with two properties:
- `array`: an array of elements (e.g., `[1, 2, 3]`)
- `callbackStr`: a string representing a callback function (e.g., `"(x) => x * 2"`)

---

## 📤 Output Format

An array where each element is the result of applying the callback to the corresponding element in the original array.

---

## 🧪 Example

```json
Input:
{
  "array": [1, 2, 3],
  "callbackStr": "(x) => x * 2"
}

Output:
[2, 4, 6]
```

---

## ✅ JavaScript Solution

```js
Array.prototype.myMap = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    result.push(callback(this[i], i, this));
  }
  return result;
};
```

---

## 📜 Full Code with Input Handler

```js
Array.prototype.myMap = function(callback) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    result.push(callback(this[i], i, this));
  }
  return result;
};

// Please don't touch the code below
function solve(input) {
  const { array, callbackStr } = input;
  const callback = eval(callbackStr);
  return array.myMap(callback);
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

- You extend `Array.prototype` with a custom `myMap` method.
- It loops through the array using a `for` loop.
- For each element, it applies the callback and pushes the result to a new array.
- It returns the final transformed array — just like `map()`.

---

## 🏷️ Tags

`#JavaScript` `#Easy` `#Polyfill` `#Prototype` `#ArrayMethods` `#D10`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me!
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐙 [github.com/dpvasani](https://github.com/dpvasani)  
💼 [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
📢 [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---

