# 10 - Shared State of Modules

Week 32.4 | Thursday, August 10, 2023 | 12:04 AM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md) - [08 - Modules](08%20-%20Modules.md) - [09 - More on Modules](09%20-%20More%20on%20Modules.md) - [11 - Object Factory](11%20-%20Object%20Factory.md)

Source : [Node.js Tutorial for Beginners - 10 - Shared State of Modules](https://www.youtube.com/watch?v=Fo7IRCjrxMk&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=10)

Shared module or a shared object.

Whenever you use modules, in Node.js, the default behavior is to share the module from
"movies.js" (`module.exports = {favMovie: ""}`) among every other file that imports it.

In the example below this means that "nana.js" that file changes the object directly, and
"popo.js" gets the same changes as well.

Both "nana.js" and "popo.js" do not get a copy of (`module.exports = {favMovie: ""}`), but
instead gets reference of that exact same module found in "movies.js"

```js
//movies.js
module.exports = {
  // empty string for now because we don't know what the user's favorite movie is yet
  favMovie: "",
};
```

```js
//nana.js - a user module
var movies = require("./movies");
movies.favMovie = "Death Note";
console.log("Nana's favorite movie is: " + movies.favMovie);
// > Nana's favorite movie is: Death Note
```

```js
// popo.js - a user module
var movies = require("./movies");
console.log("Popo's favorite movie is: " + movies.favMovie);
// > Popo's favorite movie is:
```

This may be the exact functionality you'd want (e.g. users in a chat room and all users see
the same chat log) and is better for performance in memory. This is because instead of every
single different module making a copy they instead all reference the same of that module.

```js
// app.js - our starting point
require("./nana");
require("./popo");
// > Nana's favorite movie is: Death Note
// > Popo's favorite movie is: Death Note
```

To get the behavior you'd expect you'd have to keep track of the `require()` import order.

```js
// app.js - our starting point - different import order
// Oder matters had the require imports been swapped the output changes
require("./popo");
require("./nana");
// > Popo's favorite movie is:
// > Nana's favorite movie is: Death Note
```

This is not optimal and use of [object factories](../../3-permanent-notes-🧲/Object%20Factory.md) would allow each user, each module/script,
their own copy of the imported module.
