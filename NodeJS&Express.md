# Node JS & Express Cheatsheet

- - -

#### Import modules

```javascript
 const http = require("http");
```

To import External modules, you use **NPM**

- - -

## Express
- Express is a Node framework that allows you to build Node programs with more features, less code and a better structure.

#### Install Express

```
npm install express
```

#### First Example

```javascript
// Import Express
const express = require("express");

// New constant that represents the Express module
const app = express();

//Port to listen
const port = 3000;

// The request for the root of the server. Then, it send the result.
app.get("/", (req,res)=> res.send("Hello Node!"));

// Listen on a specific port for any HTTP request that comes to our server
app.listen(port, ()=>console.log(`Listening at port ${port} !!`))
```

#### Setting Different routes

```javascript
// Import Express
const express = require("express");
const app = express();

//http://localhost:3000/
app.get("/", (req, res) => {
  res.send("Root");
});

//http://localhost:3000/Contact
app.get("/contact", (req, res) => {
  res.send("Contact Page");
});

app.listen(3000);


```



&nbsp;
- - -

 ### Nodemon

 Nodemon is an utiliy that will monitor any changes inside your scripts, so when any changes are made, you will **NOT** have to restart the server.

```
npm install -g nodemon

nodemon server.js
```



- - -



- What is node?
- how it works
- commands
- setup
- dictionary
- global variables
- syntax
-  function vs function expressions
- Module and require
- 
- - -
