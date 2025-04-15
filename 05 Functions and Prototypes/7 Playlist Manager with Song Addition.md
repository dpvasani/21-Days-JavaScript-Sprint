# 📝 Playlist Manager with Song Addition

> **Difficulty:** Easy  
> **Sprint:** JavaScript Sprint
> **Category:** Prototypes

---

## Problem Statement

Create a `Playlist` constructor function that initializes an empty `songs` array.  
You need to implement a method `addSong(song)` on the prototype which adds the given `song` to the `songs` array.

---

## Input Format

The input is a JSON object containing a single key:

- `song`: A string representing the name of the song to be added.

### Example Input

```json
{
  "song": "Bohemian Rhapsody"
}
```

---

## Output Format

The output should be the array of songs after adding the new song.

### Example Output

```json
["Bohemian Rhapsody"]
```

---

## JavaScript Solution

```js
function Playlist() {
  // Initialize songs property
  this.songs = [];
}

// Define addSong method on Playlist's prototype
Playlist.prototype.addSong = function(song) {
  this.songs.push(song);
};

// Please don't remove the code below
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout,
});

rl.on('line', (input) => {
  const { song } = JSON.parse(input);
  const playlist = new Playlist();
  playlist.addSong(song);
  process.stdout.write(JSON.stringify(playlist.songs));
});
```

---

## 🏷️ Tags

`#JavaScript` `#Prototypes` `#Playlist` `#SongManager` `#ConstructorFunction`

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
