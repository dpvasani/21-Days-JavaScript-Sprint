# 📝 Triwizard Maze Navigation

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint  
> **Category:** Logic

---

## Problem Statement

Harry is in a magical maze where every step moves him exactly one unit in a certain direction:
- `"N"` = move north (up)
- `"S"` = move south (down)
- `"E"` = move east (right)
- `"W"` = move west (left)

He starts at the origin `(0, 0)`.

You're given an array of directions (like `["N", "S", "W"]`). Each string represents a move Harry makes. Your task is to return `true` if Harry ends up exactly where he started, and `false` otherwise.

---

## Input Format

The input is a list of strings, each one being either `"N"`, `"S"`, `"E"`, or `"W"`. The list may be empty (in which case Harry stays at the start).

### Example Input

```json
["N", "S", "E", "W"]
```

---

## Output Format

Return `true` if Harry ends up back at the origin `(0, 0)` after following all the directions. Otherwise, return `false`.

### Example Output

```json
true
```

---

## JavaScript Solution

```js
function solve(input) {
  // Initialize the starting position at (0, 0)
  let x = 0, y = 0;
  
  // Loop through each direction in the input array
  for (let direction of input) {
    switch (direction) {
      case "N":
        y += 1; // Move north (up)
        break;
      case "S":
        y -= 1; // Move south (down)
        break;
      case "E":
        x += 1; // Move east (right)
        break;
      case "W":
        x -= 1; // Move west (left)
        break;
    }
  }
  
  // If Harry is back at the origin, return true; otherwise, false
  return x === 0 && y === 0;
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const directions = JSON.parse(input);
  const result = solve(directions);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Logic` `#Maze` `#Direction`

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