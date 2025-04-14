# 📝 Student Grading System

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 4)  
> **Category:** Conditionals

---

## Problem Statement

You are building a grading tool. The logic for assigning grades based on scores is as follows:

- **Score ≥ 90:** Grade is `"A"`
- **Score between 80 and 89 (inclusive):** Grade is `"B"`
- **Score between 70 and 79 (inclusive):** Grade is `"C"`
- **Score between 60 and 69 (inclusive):** Grade is `"D"`
- **Invalid Inputs:** If the input is a non-number or a number outside the range of 0–100, return `"Invalid"`.

---

## Input Format

The input is a number, `score`, representing the student's score.

### Example Input

```json
95
```

---

## Output Format

Return a string that represents the grade based on the score. If the score is invalid, return `"Invalid"`.

### Example Output

```json
"A"
```

---

## Constraints

- The `score` will be an integer.
- The input value will be considered invalid if:
  - It is not a number.
  - It is a number outside the range of 0–100.

---

## JavaScript Solution

```js
function solve(score) {
  if (typeof score !== 'number' || score < 0 || score > 100) return "Invalid";

  if (score >= 90) return "A";
  if (score >= 80) return "B";
  if (score >= 70) return "C";
  if (score >= 60) return "D";

  return "F";
}


// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (input) => {
  const score = JSON.parse(input);
  const result = solve(score);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Conditionals` `#Grading` `#Logic`

---

## ✍️ Author

**Darshan Vasani**  
[Website](https://dpvasani56.vercel.app/) | [GitHub](https://github.com/dpvasani) | [LinkedIn](https://linkedin.com/in/dpvasani56)

---
