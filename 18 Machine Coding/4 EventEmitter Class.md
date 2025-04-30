# 🗂️ EventEmitter Class

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint (Day 21)  
> **Category:** Class Implementation | Event Handling

---

## 🧩 Problem Statement

You are tasked with implementing a class `EventEmitter` that simulates an event-based system. The class should support the following operations:

1. **on(eventName, callback)**: Register a callback for a given event.
2. **off(eventName, callback)**: Unregister a previously registered callback for an event.
3. **emit(eventName, ...args)**: Trigger all registered callbacks for the event, passing any arguments to them.

### Methods:

- **on(eventName, callback)**: Registers a callback for the event `eventName`.
- **off(eventName, callback)**: Removes a previously registered callback for the event `eventName`.
- **emit(eventName, ...args)**: Calls all registered callbacks for the event `eventName`, passing any additional arguments.

---

## 📥 Input Format

The input is an array of arrays, where each sub-array represents an operation to be executed. Operations can be:
1. **"on"**: Register a callback.
2. **"off"**: Unregister a callback.
3. **"emit"**: Emit an event.

Each operation includes the event name and the associated callback (if applicable).

### Example Input:

```json
[
  ["on", "play", "cb1"],
  ["emit", "play", "song1"]
]
```

---

## 📤 Output Format

The output should be an array of strings, where each string is the result of executing the registered callbacks for the emitted events.

### Example Output:

```json
["cb1: song1"]
```

---

## 🧪 Test Case

### Input:

```json
[
  [["on", "play", "cb1"], ["emit", "play", "song1"]]
]
```

### Output:

```json
["cb1: song1"]
```

---

## ✅ JavaScript Solution

### 🔑 Key Concepts

- **Event-driven architecture** for handling events.
- **Callback management** with `on`, `off`, and `emit`.
- **Array handling** for managing event listeners and their order.

---

### JavaScript Code:

```js
class EventEmitter {
  constructor() {
    this.events = {};  // Store event listeners for each event name
  }

  // Register a callback for the event
  on(eventName, callback) {
    if (!this.events[eventName]) {
      this.events[eventName] = [];  // Initialize the event if it doesn't exist
    }
    this.events[eventName].push(callback);  // Add the callback to the list of listeners
  }

  // Unregister a callback for the event
  off(eventName, callback) {
    if (!this.events[eventName]) return;

    // Remove the callback from the event listeners
    this.events[eventName] = this.events[eventName].filter(cb => cb !== callback);
  }

  // Trigger the event and call all registered callbacks with the provided arguments
  emit(eventName, ...args) {
    if (!this.events[eventName]) return;

    // Call each callback with the provided arguments
    for (const callback of this.events[eventName]) {
      callback(...args);
    }
  }
}

// Don't touch below this
function solve(input) {
  const emitter = new EventEmitter();
  const [calls] = input;

  const logs = [];
  const callbacks = {
    cb1: (...args) => logs.push("cb1:" + args.join(",")),
    cb2: (...args) => logs.push("cb2:" + args.join(",")),
    cb3: (...args) => logs.push("cb3:" + args.join(",")),
  };

  for (const call of calls) {
    const [action, eventName, ...rest] = call;

    if (action === "on") {
      const [cb] = rest;
      emitter.on(eventName, callbacks[cb]);
    } else if (action === "off") {
      const [cb] = rest;
      emitter.off(eventName, callbacks[cb]);
    } else if (action === "emit") {
      emitter.emit(eventName, ...rest);
    }
  }

  return logs;
}

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

- **Event Listeners**: Manage multiple listeners for a single event.
- **Callback Removal**: Efficiently remove specific callbacks.
- **Emit Event**: Execute callbacks in the order they were added.

---

## 🏷️ Tags

`#EventEmitter` `#CallbackManagement` `#EventHandling` `#JavaScript`

---

## 👨‍💻 Author

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**

### 🔗 Connect with me  
🌐 [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐱 [GitHub](https://github.com/dpvasani) | 👔 [LinkedIn](https://linkedin.com/in/dpvasani56)  
📢 [Topmate](https://topmate.io/dpvasani56) | 🌲 [Linktree](https://linktr.ee/dpvasani56)

---
