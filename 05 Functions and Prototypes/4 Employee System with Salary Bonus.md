# 📝 Employee System with Salary Bonus

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint 
> **Category:** Prototypes

---

## Problem Statement

Create an Employee constructor that initializes `name`, `position`, and `salary`. Implement a method `applyBonus(percent)` that increases the salary by the given percentage.

### Challenge:
- Implement an `Employee` constructor with `name`, `position`, and `salary`.
- Attach a method `applyBonus(percent)` to the prototype to increase the salary based on the given percentage.

---

## Input Format

The input consists of an employee’s `name`, `position`, `salary`, and `bonus` (percentage increase).

### Example Input

```json
{
  "name": "John Doe",
  "position": "Software Engineer",
  "salary": 50000,
  "bonus": 10
}
```

---

## Output Format

The output should be the updated salary after applying the bonus.

### Example Output

```json
55000
```

---

## JavaScript Solution

```js
function Employee(name, position, salary) {
  // Initialize name, position, and salary properties
  this.name = name;
  this.position = position;
  this.salary = salary;
}

// Define applyBonus method on Employee's prototype
Employee.prototype.applyBonus = function(percent) {
  this.salary += this.salary * (percent / 100);
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { name, position, salary, bonus } = JSON.parse(input);
  const employee = new Employee(name, position, salary);
  employee.applyBonus(bonus);
  process.stdout.write(JSON.stringify(employee.salary));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#EmployeeSystem` `#SalaryBonus` `#Methods`

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