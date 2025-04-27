# Understanding Our To do List App 🌟

Hey there! Let's explore how our todo list web app works. We'll break down the main file (server.js) into easy-to-understand parts.

## 1. Getting Started 🚀

```javascript
const express = require('express');
const path = require('path');
const fs = require('fs');
```

Think of this part like packing your backpack for school. We're grabbing three important tools:
- `express`: This is like our web app's brain - it helps us create a website
- `path`: This helps us find files on our computer, like a digital map
- `fs`: This lets us read and write files (like saving your todo list info!)

## 2. Setting Up Our Web App 🛠️

```javascript
const app = express();
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
app.use(express.static('public'));
```

This is like setting up a lemonade stand:
- We create our app (like setting up the stand)
- We tell it how to understand information from users (like having a menu)
- We set up a public folder for things everyone can see (like putting up signs)

## 3. Working with Files 📁

```javascript
const usersFilePath = path.join(__dirname, 'data', 'todolist.json');
if (!fs.existsSync(path.join(__dirname, 'data'))) {
  fs.mkdirSync(path.join(__dirname, 'data'));
}
```

This is like creating a filing system:
- We make sure we have a special folder called 'data'
- If it doesn't exist, we create it
- This is where we'll store players' scores information

## 4. Handling Web Pages 🌐

We only have one webpage to demonstrate the CRUD processes

```javascript
app.get('/', (req, res) => {
  res.render('index.hbs');
});

```

## 5. Processing Form Submissions ✍️

There are several form submissions one for Edit, one for Delete and one for Creating/Saving New player score.

```javascript
app.post('/save', (req, res) => { // for Creating 
  let toDo = req.body;
  // to edit player score
});

app.get('/delete', (req, res) => { // for Deleting
   let toDo = req.query;
  // to edit player score
});
```
## 6. Starting the Web Server 🌍

```javascript
app.listen(3000, '0.0.0.0', () => {
  console.log(`Server is running on port 3000`);
});
```

Remember: This is a real web application that you can interact with - just like the big websites you use every day! The main difference is that we've made it simple and focused on zodiac signs. 🌟
