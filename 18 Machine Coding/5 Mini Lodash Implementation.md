# 🛠️ Mini Lodash Implementation

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Utility Functions

---

## 🧩 Problem Statement

Implement a utility object `miniLodash` that replicates the behavior of three widely-used utility functions found in libraries like Lodash:

1. **`chunk(array, size)`**: Splits the array into chunks of the specified size. The last chunk may be smaller if not divisible evenly.
2. **`groupBy(array, keyOrFn)`**: Groups items in the array by a specified key or transformation function.
    - If `keyOrFn` is a string, group by property name.
    - If `keyOrFn` is a function, use its result as the grouping key.
3. **`uniqBy(array, keyOrFn)`**: Removes duplicates based on a derived key.
    - If `keyOrFn` is a string, uniqueness is based on the property.
    - If `keyOrFn` is a function, it determines the key to compare for uniqueness.

---

## 📥 Input Format

The input will be an array where:
- The first element is the method name (either `chunk`, `groupBy`, or `uniqBy`).
- The following elements are the arguments for the method.

### Example Input:

```json
["chunk", [1, 2, 3, 4, 5, 6], 2]
```

---

## 📤 Output Format

The output will be the result of the utility function called with the provided arguments.

### Example Output:

```json
[[1, 2], [3, 4], [5, 6]]
```

---

## 🧪 Test Case

### Input:

```json
["chunk", [1, 2, 3, 4, 5, 6], 2]
```

### Output:

```json
[[1, 2], [3, 4], [5, 6]]
```

---

## ✅ JavaScript Solution

### 🔑 Key Concepts

- **Array Manipulation**: Using array methods like `map`, `filter`, and `reduce`.
- **Grouping Logic**: Using either strings or functions for grouping.
- **Uniqueness Logic**: Checking uniqueness based on properties or derived values.

---

### JavaScript Code:

```js
const miniLodash = {
  // Chunk function: Splits an array into chunks of the given size
  chunk(array, size) {
    const result = [];
    for (let i = 0; i < array.length; i += size) {
      result.push(array.slice(i, i + size));
    }
    return result;
  },

  // GroupBy function: Groups elements of an array by a key or function
  groupBy(array, keyOrFn) {
    let getKey;

    // Convert stringified function to actual function if needed
    if (typeof keyOrFn === 'string' && keyOrFn.trim().startsWith('(')) {
      getKey = eval(keyOrFn); // Not recommended to use eval; be cautious
    } else if (typeof keyOrFn === 'string') {
      getKey = (item) => item[keyOrFn];
    } else {
      getKey = keyOrFn;
    }

    return array.reduce((acc, item) => {
      const key = getKey(item);
      if (!acc[key]) acc[key] = [];
      acc[key].push(item);
      return acc;
    }, {});
  },

  // UniqBy function: Removes duplicates from an array based on a key or function
  uniqBy(array, keyOrFn) {
    let getKey;

    // Convert stringified function to actual function if needed
    if (typeof keyOrFn === 'string' && keyOrFn.trim().startsWith('(')) {
      getKey = eval(keyOrFn); // Not recommended to use eval; be cautious
    } else if (typeof keyOrFn === 'string') {
      getKey = (item) => item[keyOrFn];
    } else {
      getKey = keyOrFn;
    }

    const seen = new Set();
    const result = [];
    for (const item of array) {
      const key = getKey(item);
      if (!seen.has(key)) {
        seen.add(key);
        result.push(item);
      }
    }
    return result;
  },
};
```

---

## 🧾 Full Code with Input Handler

```js
const miniLodash = {
  // Chunk function: Splits an array into chunks of the given size
  chunk(array, size) {
    const result = [];
    for (let i = 0; i < array.length; i += size) {
      result.push(array.slice(i, i + size));
    }
    return result;
  },

  // GroupBy function: Groups elements of an array by a key or function
  groupBy(array, keyOrFn) {
    let getKey;

    // Convert stringified function to actual function if needed
    if (typeof keyOrFn === 'string' && keyOrFn.trim().startsWith('(')) {
      getKey = eval(keyOrFn); // Not recommended to use eval; be cautious
    } else if (typeof keyOrFn === 'string') {
      getKey = (item) => item[keyOrFn];
    } else {
      getKey = keyOrFn;
    }

    return array.reduce((acc, item) => {
      const key = getKey(item);
      if (!acc[key]) acc[key] = [];
      acc[key].push(item);
      return acc;
    }, {});
  },

  // UniqBy function: Removes duplicates from an array based on a key or function
  uniqBy(array, keyOrFn) {
    let getKey;

    // Convert stringified function to actual function if needed
    if (typeof keyOrFn === 'string' && keyOrFn.trim().startsWith('(')) {
      getKey = eval(keyOrFn); // Not recommended to use eval; be cautious
    } else if (typeof keyOrFn === 'string') {
      getKey = (item) => item[keyOrFn];
    } else {
      getKey = keyOrFn;
    }

    const seen = new Set();
    const result = [];
    for (const item of array) {
      const key = getKey(item);
      if (!seen.has(key)) {
        seen.add(key);
        result.push(item);
      }
    }
    return result;
  },
};

// Input handler
function solve(input) {
  const [method, ...args] = input;
  const result = miniLodash[method](...args);
  return result;
}

// Setting up readline interface for input
const readline = require('readline');
const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

// Listening for input
rl.on('line', (line) => {
  const input = JSON.parse(line);  // Parsing input into JSON format
  const result = solve(input);  // Solving the problem
  process.stdout.write(JSON.stringify(result));  // Output result
});
```

---

## 🧠 Key Concepts

- **Array Chunking**: Efficiently breaking up an array into smaller pieces using `slice`.
- **Grouping by Key**: Using either a property name or a function to group items.
- **Uniqueness Filtering**: Using a `Set` to track uniqueness based on a key.

---

## 🏷️ Tags

`#miniLodash` `#ArrayUtilities` `#JavaScript` `#FunctionalProgramming`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---

