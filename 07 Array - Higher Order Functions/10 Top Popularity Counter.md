# 🔥 Top Popularity Counter

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 9)  
> **Category:** Objects / Arrays / Frequency Count

---

## Problem Statement

You manage blog posts. Each blog post contains a title and an array of tags.

Return an object showing the total **count per tag** across all posts.

---

## Input Format

An array of objects.  
Each object has:
- `title`: a string
- `tags`: an array of strings

---

## Output Format

An object where each key is a tag and the value is the number of times it appears.

---

### Example

```json
Input:
[
  { "title": "Post A", "tags": ["js", "web"] },
  { "title": "Post B", "tags": ["js", "node"] },
  { "title": "Post C", "tags": ["web", "design", "js"] }
]

Output:
{
  "js": 3,
  "web": 2,
  "node": 1,
  "design": 1
}
```

---

## JavaScript Solution

```js
function solve(input) {
  const tagCount = {};

  input.forEach(post => {
    post.tags.forEach(tag => {
      tagCount[tag] = (tagCount[tag] || 0) + 1;
    });
  });

  return tagCount;
}
```

---

## Full Code with Input Handler

```js
function solve(input) {
  const tagCount = {};

  input.forEach(post => {
    post.tags.forEach(tag => {
      tagCount[tag] = (tagCount[tag] || 0) + 1;
    });
  });

  return tagCount;
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

- Loop through each post in the input.
- For each post’s tags array, count each tag using a frequency map.
- Use the tag as a key in an object and increment its value.

---

## 🏷️ Tags

`#JavaScript` `#Hard` `#Objects` `#Arrays` `#FrequencyCounter` `#TagSystem` `#D9`

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