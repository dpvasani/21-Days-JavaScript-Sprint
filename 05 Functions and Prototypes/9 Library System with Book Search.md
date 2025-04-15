# 🏛️ Library System with Book Search

> **Difficulty:** Medium  
> **Sprint:** JavaScript Sprint 
> **Category:** Prototypes

---

## Problem Statement

You are designing a basic **Library System**.  
Create a `Library` constructor that initializes:

- A `books` array to hold book entries (strings representing book titles).

### Implement the following prototype methods:

1. **addBook(book)**  
   - Adds a book title (string) to the `books` array.

2. **findBook(title)**  
   - Searches for the given `title` in the books array.  
   - Returns `"Book found"` if the title exists.  
   - Returns `"Book not found"` otherwise.

---

## Input Format

The input contains:

- `books`: An array of book titles to add.
- `searchTitle`: A single title to search in the library.

### Example Input

```json
{
  "books": ["The Alchemist", "Clean Code", "JavaScript: The Good Parts"],
  "searchTitle": "Clean Code"
}
```

---

## Output Format

Return a string indicating whether the book was found or not.

### Example Output

```json
"Book found"
```

---

## JavaScript Solution

```js
function Library() {
  this.books = [];
}

// Define addBook method on Library's prototype
Library.prototype.addBook = function(book) {
  this.books.push(book);
};

// Define findBook method on Library's prototype
Library.prototype.findBook = function(title) {
  return this.books.includes(title) ? "Book found" : "Book not found";
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { books, searchTitle } = JSON.parse(input);
  const library = new Library();

  books.forEach(book => library.addBook(book));

  process.stdout.write(JSON.stringify(library.findBook(searchTitle)));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#LibrarySystem` `#Search` `#OOP`

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