# 🎂 Birthday Countdown

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint (Day 15)  
> **Category:** Date Handling

---

## 🧩 Problem Statement

A person wants to know **how many days** are left until their next birthday.  
You are given:
- `today` (string in `"YYYY-MM-DD"` format)
- `birthday` (string in `"MM-DD"` format)

Return the **number of days left** until the next occurrence of their birthday.

**Note:**  
- If the birthday has already passed this year, calculate it for the next year.
- Assume all dates are valid.

---

## 📥 Input Format

```js
{
  today: "YYYY-MM-DD",
  birthday: "MM-DD"
}
```

Example:
```js
{ today: "2025-04-26", birthday: "06-10" }
```

---

## 📤 Output Format

```js
number
```

Number of days left until the next birthday.

Example:
```js
45
```

---

## ✅ JavaScript Solution

```js
function solve(input) {
  const { today, birthday } = input;

  const [year, month, day] = today.split('-').map(Number);
  const [bMonth, bDay] = birthday.split('-').map(Number);

  let birthdayDate = new Date(year, bMonth - 1, bDay);
  const todayDate = new Date(year, month - 1, day);

  // If birthday already passed this year, move to next year
  if (birthdayDate < todayDate) {
    birthdayDate = new Date(year + 1, bMonth - 1, bDay);
  }

  const diffTime = birthdayDate - todayDate;
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));

  return diffDays;
}
```

---

## 📜 Full Code with Input Handler

```js
function solve(input) {
  const { today, birthday } = input;

  const [year, month, day] = today.split('-').map(Number);
  const [bMonth, bDay] = birthday.split('-').map(Number);

  let birthdayDate = new Date(year, bMonth - 1, bDay);
  const todayDate = new Date(year, month - 1, day);

  // If birthday already passed this year, move to next year
  if (birthdayDate < todayDate) {
    birthdayDate = new Date(year + 1, bMonth - 1, bDay);
  }

  const diffTime = birthdayDate - todayDate;
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));

  return diffDays;
}

// Please don't touch the code below
const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', (line) => {
  const input = JSON.parse(line);
  const result = solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **Date Parsing:** Split and convert strings to `Date` objects.
- **Date Comparison:** Compare two `Date` objects.
- **Milliseconds to Days:** Convert time difference into full days.

---

## 🧪 Example

```js
Input:
{ today: "2025-04-26", birthday: "06-10" }

Output:
45

Input:
{ today: "2025-12-30", birthday: "01-02" }

Output:
3
```

---

## 🏷️ Tags

`#JavaScript` `#DateHandling` `#Set` `#Countdown`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)  

---

