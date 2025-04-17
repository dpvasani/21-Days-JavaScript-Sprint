# 🎓 Student Grade Filter

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 8)  
> **Category:** Arrays / Filter / Objects

---

## Problem Statement

You receive a list of students, where each student is represented as an object with:

```js
{ name: string, grade: number }
```

Write a function `solve(input)` that returns an array of names of students who scored **at least 75**.

> 💡 Filter based on the grade, and return only the names of qualifying students.

---

## Input Format

An array of student objects:
- `name`: a string representing the student's name.
- `grade`: a number representing the student's grade.

---

## Output Format

An array of strings (student names) who scored **75 or more**.

---

### Example:

```json
Input: [
  { "name": "Alice", "grade": 85 },
  { "name": "Bob", "grade": 72 },
  { "name": "Charlie", "grade": 90 }
]
Output: ["Alice", "Charlie"]
```

---

## JavaScript Solution

```js
function solve(input) {
  return input
    .filter(student => student.grade >= 75)
    .map(student => student.name);
}
```

---

## Code with Test Handler

```js
// Your task is to implement this function
function solve(input) {
  return input
    .filter(student => student.grade >= 75)
    .map(student => student.name);
}

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Explanation

- Use `filter()` to find students with `grade >= 75`.
- Use `map()` to extract only their names.
- A great example of chaining array methods.

---

## 🏷️ Tags

`#JavaScript` `#Filter` `#Map` `#Objects` `#Arrays` `#GradingSystem` `#Interview`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me!  
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app)  
🐙 [github.com/dpvasani](https://github.com/dpvasani)  
💼 [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
📢 [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---
