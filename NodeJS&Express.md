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
&nbsp;
#### Setting Different routes

```javascript
//http://localhost:3000/
app.get("/", (req, res) => {
  res.send("Root");
});

//http://localhost:3000/Contact
app.get("/contact", (req, res) => {
  res.send("Contact Page");
});
```

&nbsp;
#### Sending Files
You can send a file as a response. With this, you will be able to send HTML files on every specific route:

```javascript
app.get("/", (req,res)=>{
    res.sendFile(__dirname + "/index.html")
});
```
The **__dirname** is the current location you are in. Because the program is going to run on a server, we do not know the specific directory,this is what this global variable is for.



&nbsp;
- - -
 ## Nodemon

 Nodemon is an utiliy that will monitor any changes inside your scripts, so when any changes are made, you will **NOT** have to restart the server.

```
npm install -g nodemon

nodemon server.js
```

- - -
## Body Parser

Body Parser is an NPM Package that allows you to get the data passed from the post request.
```
 npm install body-parser
```

- - -

## Examples

### Get post request data
For this, you need to have **BODY PARSER** installed

```javascript

const express = require("express");
const bodyParser = require("body-parser");
const app = express();

app.use(bodyParser.urlencoded({extended:true}))


app.get("/", (req,res)=>{
    res.sendFile(__dirname + "/index.html")
});

app.post("/", (req,res)=>{
    console.log(req.body)
    res.send("Success")
})

app.listen(3000)  

```

- - -

## APIs

API stands for **A**pplication **P**rogramming **I**nterfaces.
They are a set of commands, functions, protocols and objects that are used to **create software** and interact with an **external system**.
 
 &nbsp;
 
- ***Endpoint***

An endpoint es the end of a communication channel. Each endpoint is the location from which APIs can access the resources they need to carry out their function. 
APIs work using ‘requests’ and ‘responses.’ When an API requests information from a web application or web server, it will receive a response. The place that APIs send requests and where the resource lives, is called an endpoint.

 &nbsp;

- ***Paths***

The path comes after the endpoint. When you call an api, you specify the path in order to get the data I want.

You can think of the endpoint as a Github repo and a path as a specific branch.


   &nbsp;

- ***Parameters***

The parameters comes after the path. You need to add a question mark and specify them.
They are like variables. 
They are used to pass keys with values in order to modify the response according to those parameters.

   &nbsp; 

- ***Authentication***
The authentication in Node is used to identify the person that is trying to use their API. you can modify it to send specific things depending if he is authenticated or not.

It has another names, like **API Key**, **id**, etc.
The authentication is also a **Parameter**.

&nbsp;

- - -
## JSON
JSON stands for **J**ava**S**cript **O**bject **N**otation.

They are almost the same as a Javascript Object.

It is commonly used to **Pass Data** through APIs, and receive it as a Javascript Object.

&nbsp;
- - -

## RESTful API

**REST** stands for **RE**presentational **S**tate **T**ransfer. 
It is just an architectural **structure** for designing APIs.

You need to follow certain rules in order to be RESTful.
The 2 most important are:
  - Use HTTP request language.
  - Use specific pattern of routes/endpoint URLs.

Yuu need to use **CRUD**

- **Get** (Read): We use it when we want our server to serve up some resource. In a database, is the same to read it, filter it and send the new data as a response.
- **Post** (Create): We use it to create some data in our database. The request will **contain** the data and the response will send a status of the request.
- **Put** and **Patch** (Update): This ones goes to our database and updates some pieces of data. The difference between put and patch is that patch will only update the piece of data you want to update. While with put, you update an entire object.
- **Delete**: Deletes the specific data you pass in the database.
  

- - -



<br></br><br></br><br></br><br></br><br></br><br></br><br></br>