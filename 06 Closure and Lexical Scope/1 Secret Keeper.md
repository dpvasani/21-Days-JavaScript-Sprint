# 🕵️ Secret Keeper

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 7)  
> **Category:** Closures / State Management

---

## Problem Statement

Implement a function `secretKeeper(secret)` that returns an object with two methods:

- **unlock()**: Grants access to the secret.
- **getSecret()**: Returns the actual secret only **after** `unlock()` has been called.  
  If `unlock()` hasn’t been called yet, return `"Access Denied"`.

The object must **preserve state using closures** — meaning the unlocked status is kept private.

---

## Input Format

```json
{
  "secret": "launch codes",
  "actions": ["get", "unlock", "get", "get"]
}
```

---

## Output Format

```json
["Access Denied", "launch codes", "launch codes"]
```

---

## JavaScript Solution

```js
function secretKeeper(secret) {
  let unlocked = false;

  return {
    unlock: function () {
      unlocked = true;
    },
    getSecret: function () {
      return unlocked ? secret : "Access Denied";
    },
  };
}

// Please don't touch the code below
function solve(input) {
  const { secret, actions } = input;
  const keeper = secretKeeper(secret);
  const output = [];

  actions.forEach(action => {
    if (action === "unlock") {
      keeper.unlock();
    } else if (action === "get") {
      output.push(keeper.getSecret());
    }
  });

  return output;
}

const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Closures` `#Encapsulation` `#SecureState`

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
