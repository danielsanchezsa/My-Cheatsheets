# Complete NodeJS Developer in 2022

[Udemy Course](https://www.udemy.com/course/complete-nodejs-developer-zero-to-mastery/)

- - -

## Node Introduction

### How it was born

JavaScript is a programming language. In order to **run JS**, we need a way to make the computer understand it. This is what a **JS Engine** does. The browser that we use has an engine to read JS. But, how do you run JS without the **browser**?

When Chrome was introduced, it came with the **V8 JS engine**. With this, *Node* Was created with the idea of using that V8 engine outside the browser.

### Node Runtime

What Node JS Does, is to take a JS file, pass it to the V8 Engine, and when the engine sees something is not part of JS (Read files, connect to a DB, etc.), is going to communicate with the **libuv library** (support library with a focus on asynchronous I/O).


**Node is** a JS Runtime environment for us to run JS that gives us more than a V8 engine.