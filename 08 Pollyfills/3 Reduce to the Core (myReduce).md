# 🔋 Reduce to the Core (myReduce)

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 10)  
> **Category:** Polyfill / Array.prototype / Reduce

---

## 🧩 Problem Statement

Kiran's spacecraft relies on JavaScript code to compute **battery levels**, but the environment does **not support `Array.prototype.reduce`**. Your mission is to implement a polyfill `myReduce` that behaves just like the native `reduce()` method.

---

## 📥 Input Format

An object with:
- `array`: An array of items
- `callbackStr`: A string version of the reducer function (e.g. `"(acc, val) => acc + val"`)
- `initialValue`: A starting value for the accumulator (can be a number, string, object, etc.)

---

## 📤 Output Format

The single reduced value returned from the reduction process.

---

## 🧪 Example

```json
Input:
{
  "array": [1, 2, 3, 4],
  "callbackStr": "(acc, val) => acc + val",
  "initialValue": 0
}

Output:
10
```

---

## ✅ JavaScript Solution

```js
Array.prototype.myReduce = function(callback, initialValue) {
  let accumulator = initialValue;
  let startIndex = 0;

  if (accumulator === undefined) {
    if (this.length === 0) {
      throw new TypeError('Reduce of empty array with no initial value');
    }
    accumulator = this[0];
    startIndex = 1;
  }

  for (let i = startIndex; i < this.length; i++) {
    accumulator = callback(accumulator, this[i], i, this);
  }

  return accumulator;
};
```

---

## 📜 Full Code with Input Handler

```js
Array.prototype.myReduce = function(callback, initialValue) {
  let accumulator = initialValue;
  let startIndex = 0;

  if (accumulator === undefined) {
    if (this.length === 0) {
      throw new TypeError('Reduce of empty array with no initial value');
    }
    accumulator = this[0];
    startIndex = 1;
  }

  for (let i = startIndex; i < this.length; i++) {
    accumulator = callback(accumulator, this[i], i, this);
  }

  return accumulator;
};

// Please don't touch the code below
function solve(input) {
  const { array, callbackStr, initialValue } = input;
  const callback = eval(callbackStr);
  return array.myReduce(callback, initialValue);
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

- If `initialValue` is **provided**, start from index `0`.
- If **not provided**, use the **first element** of the array as the initial accumulator and start from index `1`.
- For each element, apply the `callback` using the `accumulator` and current element.
- Return the final accumulated result.

---

## 🏷️ Tags

`#JavaScript` `#ArrayMethods` `#Reduce` `#Polyfill` `#Prototype` `#Medium` `#D10`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
Full-Stack Dev | Mentor | Community Builder  

🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐙 [github.com/dpvasani](https://github.com/dpvasani)  
🔗 [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---