# 💳 Banking System with Multiple Accounts

> **Difficulty:** Hard  
> **Sprint:** JavaScript Sprint  
> **Category:** OOP / Prototypes / Transactions

---

## Problem Statement

You are tasked with designing a **banking system** where each customer has an account with:

- An `accountNumber`
- A `holderName`
- A `balance`

You need to implement the following operations:

---

### Prototype Methods:

1. **deposit(amount)**  
   - Adds money to the balance.

2. **withdraw(amount)**  
   - Deducts the amount from the balance **only if** the balance is sufficient.  
   - Prevent overdrafts.

3. **transfer(amount, targetAccount)**  
   - Transfers money from one account to another **only if** the current account has enough balance.

---

## Input Format

```json
{
  "accounts": [
    { "accountNumber": "ACC1", "holderName": "Alice", "balance": 1000 },
    { "accountNumber": "ACC2", "holderName": "Bob", "balance": 500 }
  ],
  "transaction": {
    "type": "transfer",
    "amount": 300
  }
}
```

---

## Output Format

Returns an array of updated balances for both accounts:
```json
[700, 800]
```

---

## JavaScript Solution

```js
function BankAccount(accountNumber, holderName, balance) {
  this.accountNumber = accountNumber;
  this.holderName = holderName;
  this.balance = balance;
}

// Deposit method
BankAccount.prototype.deposit = function(amount) {
  if (amount > 0) {
    this.balance += amount;
  }
};

// Withdraw method
BankAccount.prototype.withdraw = function(amount) {
  if (amount > 0 && this.balance >= amount) {
    this.balance -= amount;
  }
};

// Transfer method
BankAccount.prototype.transfer = function(amount, targetAccount) {
  if (amount > 0 && this.balance >= amount) {
    this.balance -= amount;
    targetAccount.balance += amount;
  }
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { accounts, transaction } = JSON.parse(input);

  const acc1 = new BankAccount(
    accounts[0].accountNumber,
    accounts[0].holderName,
    accounts[0].balance
  );
  const acc2 = new BankAccount(
    accounts[1].accountNumber,
    accounts[1].holderName,
    accounts[1].balance
  );

  if (transaction.type === "deposit") {
    acc1.deposit(transaction.amount);
  } else if (transaction.type === "withdraw") {
    acc1.withdraw(transaction.amount);
  } else if (transaction.type === "transfer") {
    acc1.transfer(transaction.amount, acc2);
  }

  process.stdout.write(JSON.stringify([acc1.balance, acc2.balance]));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Banking` `#Prototypes` `#OOP` `#Transactions`

---

## 👨‍💻 Author  

### 🚀 **Darshan Vasani**  
💡 **Full-Stack Developer | Software Engineer | Mentor**    

### 🔗 Connect with me! 🌍  
🌐 **Portfolio:** [dpvasani56.vercel.app](https://dpvasani56.vercel.app/)  
🐙 **GitHub:** [github.com/dpvasani](https://github.com/dpvasani)  
💼 **LinkedIn:** [linkedin.com/in/dpvasani56](https://www.linkedin.com/in/dpvasani56/)  
🌳 **Linktree:** [linktr.ee/dpvasani56](https://linktr.ee/dpvasani56)  
🎓 **Credly:** [credly.com/users/dpvasani55](https://www.credly.com/users/dpvasani55/)  
🐦 **Twitter:** [x.com/vasanidarshan56](https://x.com/vasanidarshan56)  
📢 **Topmate:** [topmate.io/dpvasani56](https://topmate.io/dpvasani56)  

---
