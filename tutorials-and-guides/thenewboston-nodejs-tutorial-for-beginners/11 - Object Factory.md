# 11 - Object Factory

Week 32.4 | Thursday, August 10, 2023 | 11:49 PM

Related : [Object Factory](../../Object%20Factory.md)

Source : [Node.js Tutorial for Beginners - 11 - Object Factory](https://www.youtube.com/watch?v=foUHJo8ZTu0&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=11)

Any time you export an object from a module: that object gets shared among every other
module (as the default behavior for Node.js).

Any time that we want to create a new object we need to export a function that creates a
new object.

An [object factory](../../Object%20Factory.md) is an object that creates another object.

In past we had the following:

```js
//movies.js
module.exports = {
  // empty string for now because we don't know what the user's favorite movie is yet
  favMovie: "",
};
```

Now instead of setting equals to a plain object like before we assign it to an anonymous
function.

The object, `module.exports`, now creates other objects by use of the anonymous function.

```js
//movies.js
module.exports = function () {
  // This function will return a new object every single time
  return {
    favMovie: "",
  };
};
```

```js
//nana.js - a user module
var movies = require("./movies");
var nanaMovies = movies();
nanaMovies.favMovie = "Death Note"
console.log("Nani's favorite movie is: " + nanaMovies.favMovie);
// > Nani's favorite movie is: Death Note
```

```js
// popo.js - a user module
var movies = require("./movies");
var popoMovies = movies();
nanaMovies.favMovie = "Your Name"
console.log("Popo's favorite movie is: " + nanaMovies.favMovie);
// > Popo's favorite movie is:
```

```js
// app.js - our starting point
require("./nana");
require("./popo");
// > Nana's favorite movie is: Death Note
// > Popo's favorite movie is: Your Name
```