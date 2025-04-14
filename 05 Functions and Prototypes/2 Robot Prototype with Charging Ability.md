# 📝 Robot Prototype with Charging Ability

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 5)  
> **Category:** Prototypes

---

## Problem Statement

You are designing a simple robot system. Each robot has a `name` and a `batteryLevel`. The robot should have a method `charge()` that increases the battery level by 20, but it cannot exceed 100.

### Challenge:
- Implement a constructor function `Robot` that initializes `name` and `batteryLevel`.
- Attach a method `charge()` to its prototype that increases `batteryLevel` by 20, ensuring it does not go above 100.

---

## Input Format

The input contains a JSON object with the `name` of the robot and its initial `batteryLevel`.

### Example Input

```json
{
  "name": "Robo1",
  "batteryLevel": 50
}
```

---

## Output Format

The output should be the robot's `batteryLevel` after calling the `charge()` method, ensuring the battery level does not exceed 100.

### Example Output

```json
70
```

---

## JavaScript Solution

```js
function Robot(name, batteryLevel) {
  // Initialize name and batteryLevel properties
  this.name = name;
  this.batteryLevel = batteryLevel;
}

// Define charge method on Robot's prototype
Robot.prototype.charge = function() {
  // Increase batteryLevel by 20, but ensure it does not exceed 100
  if (this.batteryLevel + 20 > 100) {
    this.batteryLevel = 100;
  } else {
    this.batteryLevel += 20;
  }
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { name, batteryLevel } = JSON.parse(input);
  const robot = new Robot(name, batteryLevel);
  robot.charge();
  process.stdout.write(JSON.stringify(robot.batteryLevel));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#Robot` `#Methods` `#BatteryLevel`

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