
# MERN Cheatsheet

&nbsp;

- - -

[Udemy Link](https://www.udemy.com/course/react-nodejs-express-mongodb-the-mern-fullstack-guide/learn/lecture/16808122#overview)

## MERN

### Theory

**M**ongo DB - (Database Solution NoSQL)
 **E**xpress.js - (Node framework)
 **R**eact.js - (Browser-side JS Library)
 **N**ode.js - (Server-side JavaScript Runtime)

So, ***React*** is going to build the front-end and it will also communicate with the back-end. ***Node.JS*** is going to help us build the server, so we can manipulate, receive and send data from the Database to our Web App. ***Express*** Was created to use Node, but it allows you to write simplified code and logic. At last, we are going to use ***Mongo DB*** to build our NoSQL Database.




- - -

## React JS

- - -

## Node & Express

### Intro

&nbsp;

#### What is Node JS?
- It is a **Host** Environment for JavaScript
- It is Javascript outside the browser, so it is **NOT ONLY** for servers.
&nbsp;


#### Import libraries
In Node, you import files different You use the require method:

```javascript
const fs = require('fs');
```
&nbsp;

#### Create Server
To create a server, we will use the http module

```javascript
const http = require('http');

const server = http.createServer((req, res)=>{
    console.log("Running");
    res.end("Success!");
});

server.listen(5000);
```





&nbsp;

#### REST vs GraphQL

**API** Stands for Application Programming Interface.
**REST** Stands for Representational State transfer

The difference between REST API and GraphQL API is on how requests are received or how requests should be formatted
**Rest** uses different URLs or paths, on which you can use them to use CRUD
**GraphQL** uses only one URL and one action (CRUD), and then it accepts some query commands. So the response of a GraphQL API contains a query expression that adheres to the GraphQL standard.





- - -

## MongoDB & Mongoose

- - -

## Connections

### Node - React

There are to ways of connecting these two.

1. Host both the React app and the Node Server on the same domain.
Ex:
www.myapp.com/
This can return the Website
www.myapp.com/api
This can return the APIs

2. Have a simple server to return the React App and another server to host our Node APIs


---