# 📝 Bank Account with Transaction History

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint  
> **Category:** Prototypes

---

## Problem Statement

You are building a simple banking system.  
Create a `BankAccount` constructor that initializes:

- `balance`: A number representing the current account balance.
- `transactions`: An array that stores all the deposit and withdrawal logs.

### Implement the following methods on the prototype:

1. **deposit(amount)**  
   - Increases the `balance` by the given amount.  
   - Adds a transaction log in the format: `"Deposited x"`.

2. **withdraw(amount)**  
   - Decreases the `balance` by the given amount (if enough funds are available).  
   - Logs `"Withdrew x"` if the transaction is successful.  
   - Logs `"Insufficient balance"` if the amount exceeds the balance.

3. **getTransactionHistory()**  
   - Returns the entire transaction log as an array of strings.

---

## Input Format

The input contains:

- `balance`: Initial balance of the account.
- `transactions`: An array of transaction objects with `type` (`"deposit"` or `"withdraw"`) and `amount`.

### Example Input

```json
{
  "balance": 100,
  "transactions": [
    { "type": "deposit", "amount": 50 },
    { "type": "withdraw", "amount": 30 },
    { "type": "withdraw", "amount": 150 }
  ]
}
```

---

## Output Format

Return the transaction history as an array of strings in the order the operations were executed.

### Example Output

```json
["Deposited 50", "Withdrew 30", "Insufficient balance"]
```

---

## JavaScript Solution

```js
function BankAccount(balance) {
  this.balance = balance;
  this.transactions = [];
}

// Define deposit method on BankAccount's prototype
BankAccount.prototype.deposit = function(amount) {
  this.balance += amount;
  this.transactions.push(`Deposited ${amount}`);
};

// Define withdraw method on BankAccount's prototype
BankAccount.prototype.withdraw = function(amount) {
  if (this.balance >= amount) {
    this.balance -= amount;
    this.transactions.push(`Withdrew ${amount}`);
  } else {
    this.transactions.push("Insufficient balance");
  }
};

// Define getTransactionHistory method on BankAccount's prototype
BankAccount.prototype.getTransactionHistory = function() {
  return this.transactions;
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { balance, transactions } = JSON.parse(input);
  const account = new BankAccount(balance);

  transactions.forEach(({ type, amount }) => {
    if (type === "deposit") account.deposit(amount);
    if (type === "withdraw") account.withdraw(amount);
  });

  process.stdout.write(JSON.stringify(account.getTransactionHistory()));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#BankAccount` `#Transactions` `#OOP` `#Methods`

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

