# 14 - Simple Web File Server

Week 33.2 | Tuesday, August 15, 2023 | 10:26 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md) - [13 - Creating a Basic Server](13%20-%20Creating%20a%20Basic%20Server.md)

Source : [Node.js Tutorial for Beginners - 14 - Simple Web File Server](https://www.youtube.com/watch?v=_D2w0voFlEk&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=14)

In [13 - Creating a Basic Server](13%20-%20Creating%20a%20Basic%20Server.md) we've walked though the basics of setting up a server, listen
for user requests, and provide a response.

We will now learn how to send back HTML files, JavaScript files, and CSS.

Recall whenever you're working with files you need the Node.js module `fs`:
`var fs = require('fs');`

When building websites you generally want to build a `404 response` for any pages that does
not yet exist (e.g. the about page, contacts page, careers page). A response for when things
goes bad.

The `request` object has information about what users want (e.g. a file).
Also see [HTTP REQUEST Methods](../../3-permanent-notes-🧲/HTTP%20REQUEST%20Methods.md)

In order to send back HTML file we want to send back a "readable stream" because a basic
response is just sent back in one chunk of text; however, HTML files change often and we
don't know how large of a file it is. So we want to send the HTML file in a stream for better
performance and to ensure that we don't have any errors. This is done by the following: `fs.createReadStream("./index.html").pipe(response);`

```js
// server.js
var http = require("http"); // Import the built-in Node.js module
var fs = require("fs"); // Import the built-in Node.js module

/**404 response
 * @param {*} response - The response object that the server sends back to the client
 * @returns {void} - Returns nothing
 */
function send404Response(response) {
  // Write the response header with HTTP 404 and the content type as plain text
  response.writeHead(404, { "Content-Type": "text/plain" });
  // Write the response body with the error message
  response.write("Error 404: Page not found!");
  response.end(); // End the response process
}

/**
 * Handle a user's request to the server and send back a response to the client
 * @param {*} request - The request object sent by the client to the server
 * @param {*} response - The response object that the server sends back to the client
 */
function onRequest(request, response) {
  // Inspect the request method and URL. `/` is the root URL (homepage)
  if (request.method == "GET" && request.url == "/") {
    // Write the response header with HTTP 200 and the content type as HTML
    response.writeHead(200, { "Content-Type": "text/html" });
    // Write the response body with the HTML content
    fs.createReadStream("./index.html").pipe(response);
  } else {
    // Send a 404 response if the request is not for the homepage
    send404Response(response);
  }
}

// Create a server that listens for traffic/user's request on port 8888
http.createServer(onRequest).listen(8888);
console.log("Server has started");
// > Prints "Server has started" to the console
```

## HTML Page

```html
<!-- index.html -->
<!-- URL: http://localhost:8888/ -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Document</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>

  <body>
    <div class="container">
      <div class="header">
        <h1>My Website</h1>
      </div>
      <div class="nav">
        <ul>
          <li><a href="index.html">Home</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </div>
      <div class="content">
        <h1>Home</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quisquam,
          voluptatibus, quibusdam, voluptas, quia voluptate quod quos voluptatum
          quas quidem dolorum doloremque natus. Quisquam, voluptatibus,
          quibusdam, voluptas, quia voluptate quod quos voluptatum quas quidem
          dolorum doloremque natus.
        </p>
      </div>
      <div class="footer">
        <p>&copy; 2014 My Website</p>
      </div>
    </div>
  </body>
</html>
```
