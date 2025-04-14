# 🚗 Speeding Tickets

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 4)  
> **Category:** Conditional Logic

---

## 📝 Problem Statement

You're designing an automatic ticketing system. The rules for issuing tickets are as follows:

- If the speed is 60 or below, return **"No Ticket"**.
- If the speed is between 61 and 80, return **"Small Ticket"**.
- If the speed is above 80, return **"Big Ticket"**.
- If it’s the driver's birthday, they get a 5 km/h grace. This means the speed limit is increased by 5 km/h.

---

## 📥 Input Format

The input is an object with two properties:

- `speed`: A number representing the speed of the vehicle.
- `isBirthday`: A boolean value indicating if it's the driver's birthday.

### Example Input

```json
{ "speed": 75, "isBirthday": true }
```

---

## 📤 Output Format

- A string: `"No Ticket"`, `"Small Ticket"`, or `"Big Ticket"`, based on the speed and birthday status.

### Example Output

```json
"Small Ticket"
```

---

## 🔒 Constraints

- Speed will always be a positive integer.
- `isBirthday` will be a boolean value (`true` or `false`).

---

## 💡 Hints

- Use conditional statements to check the speed and apply the birthday grace.
  
---

## ✅ JavaScript Solution

```js
function solve({ speed, isBirthday }) {
  if (isBirthday) {
    speed -= 5; // apply birthday grace
  }

  if (speed <= 60) {
    return "No Ticket";
  } else if (speed <= 80) {
    return "Small Ticket";
  } else {
    return "Big Ticket";
  }
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  input = JSON.parse(input);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Conditionals` `#Logic` `#Birthday`

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