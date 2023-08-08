# 09 - More on Modules

Week 32.1 | Monday, August 07, 2023 | 11:57 PM

Related : [08 - Modules](08%20-%20Modules.md)

Source : https://www.youtube.com/watch?v=aNN1IKoEIdM&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=9

We've learned before that anytime we want to export code from one file and into another.
We have the source module use `module.exports` followed by `.<userDefinedVariableName>`
and assign it a value (e.g. can be assigned a function).

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
module.exports.voice = printVoice; // Don't need the parentheses
```

```js
// app.js
// Code exported from movies.js are now imported into the app.js script
var movies = require("./movies");
movies.garden(); // Uses exported function from movies.js
movies.voice();
```

The problem of doing it in the example above is that it's repetitive code:
`module.exports.garden = printGarden;` and `module.exports.voice = printVoice;`

## The common and efficient way

`modules.exports` is an object and every single file that you create it has a `module.exports `
object by default.

When ever you create a `.js` file (a module) - Node.js throws `module.exports = {};` behind
the scenes and it sets it equal to a blank/empty object.

In the early example in [08 - Modules](08%20-%20Modules.md) we were adding name and value pairs to the object (i.e
`modules.exports`).

What we can do instead is write the functions we want to be "`public`" directly inside the
object.

Instead of just writing our functions and then explicitly say what functions to export one-by-
one. We can write our functions, or variables, directly inside the `modules.exports` object.

Just like a JSON object it has a name-value pair.

```js
// movies.js
module.exports = {
  // any code in obj is what gets exported
  // <functionName> set to an anonymous function
  printGarden: function () {
    console.log("The Garden of Words: PG-13");
  },
  printVoice: function () {
    console.log("A Silent Voice : PG");
  },
  favMovie: "Kimi no Na wa",
};
```

```js
// app.js
var movies = require("./movies");
movies.printVoice();
console.log(movies.favMovie);
```
