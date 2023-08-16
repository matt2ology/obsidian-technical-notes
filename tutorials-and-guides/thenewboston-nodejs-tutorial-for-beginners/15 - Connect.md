# 15 - Connect

Week 33.2 | Tuesday, August 15, 2023 | 11:40 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md)

Source : [Node.js Tutorial for Beginners - 15 - Connect](https://www.youtube.com/watch?v=54aol-U_1es&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=15)

- [15 - Connect](#15---connect)
  - [Installation](#installation)
  - [Connect Dispatcher](#connect-dispatcher)
    - [Connect Dispatcher Code](#connect-dispatcher-code)
  - [Connect - Path](#connect---path)
    - [Connect Path Code](#connect-path-code)

Common functionality used to handle user requests can be found in a server framework
module called "Connect".

## Installation

In the terminal

```cmd
npm install connect
```

`npm`, a package manager, will go out to the internet, download the package, and install and
configure it with your project in a directory named "node_modules".

Once installed you'd just need to import, require, the module:
`var connect = require("connect");`

## Connect Dispatcher

Before we can use the `connect` framework we first need to create a "connect dispatcher" (i.e.
the core connect object). This will allow us to take the request and response arguments.

So whenever a user makes a request to the server it's going to look to the "connect
dispatcher" to determine how it wants to handle that request.

Connect dispatcher is a request handler function that dispatches requests to your functions, which is why you can use it with `http.createServer()`.

The convention is to name the "connect dispatcher" as "app": `var app = connect();`

Whenever a user connects to the website, to the server, our code will look to
`var app = connect();` to see how we want to handle the request.

We help with the request we use the method `use()`. The code to handle user request is
called "middleware".

The `use()` will queue up tasks in the corresponding order in code. Instead of calling `next()`
immediately we in the real world this one may want to have a test to see if a user has
permission to do xyz.

### Connect Dispatcher Code

```js
// server.js
var connect = require("connect");
var http = require("http");

var app = connect(); // Connect dispatcher is a request handler function

/**
 * doFirst is a request handler function that will be called by the Connect dispatcher
 * @param {*} request - The user's request
 * @param {*} response - The response to send to the user
 * @param {*} next - (Optional) The next request handler function to call
 *  in the chain of request handlers
 */
function doFirst(request, response, next) {
  console.log("Bacon");
  next(); // Call the next request handler function in the chain
  // If next() is not called, function doSecond will not be called
}

/**
 * doSecond is a request handler function that will be called by the Connect dispatcher
 * @param {*} request - The user's request
 * @param {*} response - The response to send to the user
 * @param {*} next - (Optional) The next request handler function to call
 * in the chain of request handlers
 */
function doSecond(request, response, next) {
  console.log("Tuna");
  next(); // Call the next request handler function in the chain
}

app.use(doFirst); // Register doFirst as a request handler function
app.use(doSecond); // Register doSecond as a request handler function

http.createServer(app).listen(8888); // Create HTTP server with Connect dispatcher

console.log("Server is running...");
// > Server is running...
```

## Connect - Path

The `connect` framework module is popular not only for middleware, but also to have an
optional argument of a path.

For example, you have multiple pages on your website (e.g. a profile page and a forum
page). When a user requests the profile page we can then leverage the profile function, so
we can display their profile picture or etc.

This is how'd we'd handle different user request depending on the path. Similar logic can
be used to inspect the path to figure out what request a user making (what webpage
are they trying to reach) and call a function that the corresponding HTML, CSS, and
JavaScript needed for that page.

### Connect Path Code

```js
// server.js
var connect = require("connect");
var http = require("http");

var app = connect(); // Connect dispatcher is a request handler function

/**
 * profile function is a request handler function
 * @param {*} request - HTTP request object
 * @param {*} response - HTTP response object
 */
function profile(request, response) {
  console.log("User requested profile");
}

/**
 * forum function is a request handler function
 * @param {*} request - HTTP request object
 * @param {*} response - HTTP response object
 */
function forum(request, response) {
  console.log("User requested forum");
}

app.use("/profile", profile); // Register profile function with Connect dispatcher
app.use("/forum", forum); // Register forum function with Connect dispatcher

http.createServer(app).listen(8888); // Create HTTP server with Connect dispatcher

console.log("Server is running...");
// > Server is running...
```
