# 📝 Debounce Event Logger

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 19)  
> **Category:** Debounce | Timing | Event Handling | Configurable Edge Triggers

---

## 🧩 Problem Statement

You're building a **logging system** that handles **frequent events**, such as user input or UI changes. To avoid overwhelming logs, you must **debounce** these events — meaning the system should log events **after a fixed delay**, depending on options provided.

You are to implement `eventLogger(events, delay, options)` which logs events using a **debounce mechanism** with configurable **leading** and **trailing** options:

- 🔹 `leading: true`: Log the **first event** in a debounce window.
- 🔸 `trailing: true`: Log the **last event** in a debounce window.

---

## 📥 Input Format

- `events`: An array of **strings**, representing event names.
- `delay`: A number (in **milliseconds**) specifying the debounce window.
- `options`: An object with two boolean properties:
  - `leading`: log the first event in a debounce window.
  - `trailing`: log the last event in a debounce window.

---

## 📤 Output Format

- An array of event strings that were actually logged based on debounce behavior.

---

## 🧪 Example Walkthrough

### Input:

```js
{
  "events": ["click", "scroll", "resize", "mousemove", "keydown"],
  "delay": 300,
  "options": {
    "leading": true,
    "trailing": true
  }
}
```

### Output:
The logged output depends on event timing (simulated internally). With both leading and trailing enabled:
```json
["click", "keydown"]
```

- `"click"` was logged immediately (leading),
- `"keydown"` was logged after the last event within the delay window (trailing).

---

## ✅ JavaScript Solution

We simulate event timing with timeouts and collect logs based on `leading` and `trailing` flags.

---

### JavaScript Code:

```js
function eventLogger(events, delay, options) {
  const result = [];
  let timeout = null;
  let lastEvent = null;
  let canLead = true;

  events.forEach((event, index) => {
    if (canLead && options.leading) {
      result.push(event);
      canLead = false;
    } else if (options.trailing) {
      lastEvent = event;
    }

    if (timeout) clearTimeout(timeout);
    timeout = setTimeout(() => {
      if (options.trailing && lastEvent !== null) {
        result.push(lastEvent);
        lastEvent = null;
      }
      canLead = true;
    }, delay);
  });

  return result;
}
```

---

## 📜 Full Code with Input Handler

```js
// Implement the eventLogger function
function eventLogger(events, delay, options) {
  const result = [];
  let timeout = null;
  let lastEvent = null;
  let canLead = true;

  events.forEach((event, index) => {
    if (canLead && options.leading) {
      result.push(event);
      canLead = false;
    } else if (options.trailing) {
      lastEvent = event;
    }

    if (timeout) clearTimeout(timeout);
    timeout = setTimeout(() => {
      if (options.trailing && lastEvent !== null) {
        result.push(lastEvent);
        lastEvent = null;
      }
      canLead = true;
    }, delay);
  });

  return result;
}

// Please don't touch the code below
function solve(input) {
  const result = eventLogger(input.events, input.delay, input.options);
  return new Promise((res) =>
    setTimeout(() => res(result), input.delay + 10)
  );
}

const readline = require('readline');

const rl = readline.createInterface({ input: process.stdin, output: process.stdout });

rl.on('line', async (line) => {
  const input = JSON.parse(line);
  const result = await solve(input);
  process.stdout.write(JSON.stringify(result));
});
```

---

## 🧠 Key Concepts

- **Debouncing**: Waits for a pause in events before executing.
- **Leading edge**: First event is logged.
- **Trailing edge**: Last event after delay is logged.
- **Timeout clearing** ensures only the latest "trailing" event gets logged.

---

## 🏷️ Tags

`#Debounce` `#EventHandling` `#TimingFunctions` `#JavaScriptUtilities` `#EdgeControl`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)

---
