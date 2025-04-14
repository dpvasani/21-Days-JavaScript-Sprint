# 📝 Basic Animal Prototype

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 5)  
> **Category:** Prototypes

---

## Problem Statement

You need to create a constructor function `Animal` that takes a `name` parameter. Add a method `makeSound` to its prototype, which always returns `"Some generic sound"`.

### Challenge:
- Implement a constructor function `Animal` that initializes the `name` property.
- Attach a method `makeSound` to its prototype that returns `"Some generic sound"`.

---

## Input Format

The input contains a JSON object with the `name` of the animal.

### Example Input

```json
{"name": "Lion"}
```

---

## Output Format

The output should be the result of calling `makeSound` on an `Animal` instance, which always returns `"Some generic sound"`.

### Example Output

```json
"Some generic sound"
```

---

## JavaScript Solution

```js
function Animal(name) {
  // Initialize name property
  this.name = name;
}

// Define makeSound method on Animal's prototype
Animal.prototype.makeSound = function() {
  return "Some generic sound";
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { name } = JSON.parse(input);
  const animal = new Animal(name);
  process.stdout.write(JSON.stringify(animal.makeSound()));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#Constructor` `#Methods`

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
