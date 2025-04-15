# 📝 Counter with Increment and Decrement

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint
> **Category:** Prototypes

---

## Problem Statement

You need to create a counter constructor function that initializes a `count` property to `0`.  
The counter should have two prototype methods:

1. **increment()**  
   Increases the `count` by 1.

2. **decrement()**  
   Decreases the `count` by 1.

---

## Input Format

The input is an action string which will be either `"increment"` or `"decrement"`.

### Example Input

```json
{
  "action": "increment"
}
```

---

## Output Format

The output should be the updated value of the `count` after performing the given action.

### Example Output

```json
1
```

---

## JavaScript Solution

```js
function Counter() {
  // Initialize count property
  this.count = 0;
}

// Define increment method on Counter's prototype
Counter.prototype.increment = function () {
  this.count += 1;
};

// Define decrement method on Counter's prototype
Counter.prototype.decrement = function () {
  this.count -= 1;
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { action } = JSON.parse(input);
  const counter = new Counter();

  if (action === "increment") {
    counter.increment();
  } else if (action === "decrement") {
    counter.decrement();
  }

  process.stdout.write(JSON.stringify(counter.count));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#Counter` `#Increment` `#Decrement`

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

