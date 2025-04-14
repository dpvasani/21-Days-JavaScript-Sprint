# 🧩 Custom Caesar Cipher

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 3)  
> **Category:** String Manipulation

---

## 📝 Problem Statement

Implement a custom Caesar Cipher that shifts alphabetic characters based on a given direction and shift value.

### Input:
- A list containing a string, a shift value, and a direction (`left` or `right`).
- The direction specifies the direction of the shift (`left` or `right`).
- Only alphabetic characters should be shifted, and their case (uppercase/lowercase) should be preserved.
- Non-alphabetic characters should remain unchanged.

### Example:

- **Input:** `["Abc! Z", 1, "right"]`
- **Output:** `"Bcd! A"`

- **Input:** `["Abc! Z", 1, "left"]`
- **Output:** `"Zab! Y"`

---

## 📥 Input Format

A list with:
1. A string `input` (can contain letters, digits, symbols, etc.).
2. An integer `shift` representing the number of positions to shift.
3. A string `direction` that can be either `"left"` or `"right"`.

### Example Input

```json
["Abc! Z", 1, "right"]
```

---

## 📤 Output Format

The encoded string after applying the Caesar cipher.

### Example Output

```json
"Bcd! A"
```

---

## 🔒 Constraints

- The input string will contain a mix of alphabetic and non-alphabetic characters.
- The length of the string: `1 <= input.length <= 1000`.
- The shift value: `0 <= shift <= 25`.

---

## 💡 Hints

- To shift letters, you can convert them to their ASCII values (e.g., `A` is 65, `a` is 97) and apply the shift.
- For the `right` direction, you can add the shift to the ASCII value of the character. For the `left` direction, subtract the shift.
- Use the modulus operator (`%`) to wrap around the alphabet.
- Non-alphabetic characters should be skipped and remain unchanged.

---

## ✅ JavaScript Solution

```js
function solve([input, shift, direction]) {
  let result = '';
  const shiftDirection = direction === 'right' ? 1 : -1;

  for (let char of input) {
    if (/[a-zA-Z]/.test(char)) {
      const base = char === char.toUpperCase() ? 65 : 97;
      const newChar = String.fromCharCode(
        ((char.charCodeAt(0) - base + shiftDirection * shift + 26) % 26) + base
      );
      result += newChar;
    } else {
      result += char;  // Non-alphabetic characters remain unchanged
    }
  }

  return result;
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

## 🏷️ Tags

`#JavaScript` `#CaesarCipher` `#StringManipulation`

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