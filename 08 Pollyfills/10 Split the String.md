# 🔗 Split the String (`mySplit`)

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 11)  
> **Category:** String Polyfill / Tokenization

---

## 🧩 Problem Statement

Ravi is building a tokenizer that breaks strings by a separator (like a comma or space).  
Implement a polyfill called `mySplit` that mimics the behavior of `String.prototype.split`, **without using `split`**.

---

## 📥 Input Format

```js
{
  str: "apple,banana,grape",
  separator: ","
}
```

---

## 📤 Output Format

Return an array of substrings obtained by splitting the original string on the given separator.

---

## ✅ JavaScript Polyfill Solution

```js
String.prototype.mySplit = function (separator) {
  const result = [];
  let current = '';
  const str = this;

  for (let i = 0; i < str.length; i++) {
    if (separator === '') {
      result.push(str[i]);
    } else if (str[i] === separator) {
      result.push(current);
      current = '';
    } else {
      current += str[i];
    }
  }

  if (separator !== '') result.push(current);
  return result;
};
```

---

## 📜 Full Code with Input Handler

```js
String.prototype.mySplit = function (separator) {
  const result = [];
  let current = '';
  const str = this;

  for (let i = 0; i < str.length; i++) {
    if (separator === '') {
      result.push(str[i]);
    } else if (str[i] === separator) {
      result.push(current);
      current = '';
    } else {
      current += str[i];
    }
  }

  if (separator !== '') result.push(current);
  return result;
};

// Please don't touch the code below
function solve(input) {
  const { str, separator } = input;
  return str.mySplit(separator);
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

- Custom string tokenization
- Manual string iteration
- Polyfill logic without using native methods

---

## 🧪 Example

```js
Input:
{
  "str": "one,two,three",
  "separator": ","
}

Output:
["one", "two", "three"]
```

```js
Input:
{
  "str": "abc",
  "separator": ""
}

Output:
["a", "b", "c"]
```

---

## 🏷️ Tags

`#JavaScript` `#Polyfill` `#StringMethods` `#CustomSplit` `#Hard` `#D11`

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