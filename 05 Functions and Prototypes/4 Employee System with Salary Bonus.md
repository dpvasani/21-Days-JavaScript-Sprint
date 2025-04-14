# 📝 Employee System with Salary Bonus

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 5)  
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

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
