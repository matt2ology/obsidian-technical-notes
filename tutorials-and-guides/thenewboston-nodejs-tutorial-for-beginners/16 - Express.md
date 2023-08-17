# 16 - Express

Week 33.3 | Wednesday, August 16, 2023 | 09:44 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md) - [17 - Handling User Requests](17%20-%20Handling%20User%20Requests.md)

Source : [Node.js Tutorial for Beginners - 16 - Express](https://www.youtube.com/watch?v=WH5qsGnFkBM&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=16) - [Tutorial: Create a Node.js and Express app in Visual Studio](https://learn.microsoft.com/en-us/visualstudio/javascript/tutorial-nodejs?view=vs-2022)

Express one of the popular frameworks (i.e. the functionality and the folder structure) for
Node.js

In JetBrain's InteliJ you can go to `File > New Project > Node.js and NPM > Node.js Express App`. Under options configure "Template engine" with "EJS".

This can be done with VS Code via the terminal by typing to install in current directory:

```cli
express .
```

or install with app/project name

```cli
express myApp
```

Navigate to "bin > www", run code, and by default localhost:3000 should display the webpage

## Files explained

- Bin
  - www: the start-up script - core settings - create a server - what port to listen to - kick off `app.js`
- node_modules: all the modules in addition to the core modules
- public: the files the users will be able to access
  - images
  - JavaScript
  - stylesheets
- routes: the brains behind each page
  - index.js
  - users.js
- views: the HTML for each page

## Troubleshooting Help

Suggested by [praveenojha33](https://www.youtube.com/channel/UCxif0vYbmftrDHnVC8yWPJg) in the comments.

For people using sublime or any other text editor:

```cli
npm install express
```

To make life easier, we will use a neat little module called express-generator. What this will do is it will generate a skeleton website for us, making out life a lot easier. It takes care of the basic stuff, like routes and such. To install Express Generator, simply type:

```cli
npm install express-generator -g
```

We specify the -g flag, which means that it will be global, and we can use it throughout our system. Once we finish installing it, we have to make a decision. We have to choose what rendering engine we want to use for our project. For brevity, we will use `EJS` in this tutorial, which is an awesome rendering engine that I highly recommend you look more into. To setup our bare project, just type:

```cli
express -v ejs mysite
```

This will make a new folder inside of our existing project, with the name mysite. Now, to make sure we have all of the required modules for the project, run the following command.

```cli
npm install
```

Now that we have the basic website setup, we can start it! To start the website, with a basic port, simply type:

```cli
DEBUG=mysite:* npm start
```
