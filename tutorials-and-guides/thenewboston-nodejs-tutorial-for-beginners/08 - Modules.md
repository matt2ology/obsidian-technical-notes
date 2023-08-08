# Node.js Tutorial for Beginners - 08 - Modules

Week 31.4 | Thursday, August 03, 2023 | 11:26 PM

Related :

Source : https://www.youtube.com/watch?v=9JhvjhZLsEw&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=8

"Modules" groupings of similar JavaScript code; for example, a web app where a user could
look at music, movies, and TV shows. All movie related code are broken up into its own file.

```js
// movies.js
function printGarden() {
  console.log("The Garden of Words: PG-13");
}

function printVoice() {
  console.log("A Silent Voice : PG");
}
```

Each JavaScript file code can be exported from one file and imported into another file.

Code doesn't get exported by default. Code that gets exported is determined by a variable
called `module.exports` and is appended by a variable name of your choosing (e.g. `garden` in
`module.exports.garden`).

```js
// movies.js
function printGarden() {
  console.log("The Garden of Words: PG-13");
}

function printVoice() {
  console.log("A Silent Voice : PG");
}

// Only function printGarden() is able to be exported into another file
module.exports.garden = printGarden; // Don't need the parentheses
```

When importing another module into another you set it to a variable. Note that you only
need to provide the JavaScript file name without the "`.js`" file extension when using
`require()`.

According to Bucky: some systems get confused with the file extensions because a browser
can't have access to your file system, so it doesn't do a good job looking at the extensions

We need to use `./` (look in this current/same directory), so what when you wish to
utilize/implement core modules your program won't encounter possible conflicts of
the same module names (ones that you define and ones that are built into Node.js)

```js
// app.js
// Code exported from movies.js are now imported into the app.js script
var movies = require("./movies");
movies.garden(); // Uses exported function from movies.js
// movies.printVoice() is not avaliable to be used
```

This is essentially the same as having `public` and `private` methods (e.g. `printVoice()` is only
needed within "movies.js")
