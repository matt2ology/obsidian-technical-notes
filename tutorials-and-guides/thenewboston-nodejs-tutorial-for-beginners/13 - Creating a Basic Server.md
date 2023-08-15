# 13 - Creating a Basic Server

Week 33.1 | Monday, August 14, 2023 | 10:17 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md)

Source : [Node.js Tutorial for Beginners - 13 - Creating a Basic Server](https://www.youtube.com/watch?v=pYOltVz7kL0&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=13)

Creating an basic HTTP server

Node.js is different from vanilla JavaScript because plain JavaScript was made for the web
browser; in contrast, Node.js is made to be run on a server (user connection and webpage
request/database).

To turn your Node.js code and create a server is to do the following:

Our `http` object's method `createServer` takes an argument `requestListener` is our callback
(i.e. the code we want to run when a user tries to connect to the server). Typically function
(the code) we want to run are ones that sends back a web file, a web page, or info from the
database.

When users connect the server has to be listening for a request via what port.

Our `requestListener` function `onRequest` it is going to pass in two parameters.

Two pieces of information

1. The `request` object contains information regarding the user's request, such as the URL, the HTTP method used, and the user's IP address. That is the information about the user's request. What information the user were trying to get, what webpage they were trying to connect to, etc..
2. The `response` object contains methods for sending data back to the user, such as `response.writeHead()` and `response.write()`. For example, a web file, status information (e.g. good connection, couldn't find what they were looking for, an error code) can be sent back to the user.

```js
// server.js
var http = require("http"); // Import the built-in Node.js module

function onRequest(request, response) {
  // Create a function that handles requests and sends responses
  console.log("A user made a request" + request.url); // Print the request URL to the console
  // > A user made a request/
  // > A user made a request/favicon.ico

  response.writeHead(200, { "Context-Type": "text/plain" }); // Send a response header with a 200 status code and a content-type of text/plain
  response.write("Here is some data"); // Send a response body with the text "Here is some data"
  response.end(); // End the response, so the browser knows to stop loading the page
}

http.createServer(onRequest).listen(8888); // Create a server that listens for traffic/user's request on port 8888
console.log("Server has started");
// > Prints "Server has started" to the console
```

`console.log("A user made a request" + request.url);` produces two outputs

1. "A user made a request/"
2. "A user made a request/favicon.ico"

because when a user connects to the server the user's browser sends a request for the page they were looking for and, behind the scenes, a request for "favicon" (i.e. the logo of the website).

The `response.writeHead()` method sends a response header to the request. The first argument is the status code, which is 200 in this case. The second argument is an object containing the response headers. The `response.write()` method sends a response body to the request.

The `response.end()` method ends the response process. This method must be called on each response.
