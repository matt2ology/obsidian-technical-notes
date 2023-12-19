# 03 - Basic Concepts

Week 31.2 | Tuesday, August 01, 2023 | 10:39 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md)

Source : [Node.js Tutorial for Beginners - 3 - Basic Concepts](https://www.youtube.com/watch?v=jiSFfpw3Btc&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=3)

When you make objects in Node.js is the same as one would do in JavaScript.

Any Node.js codes runs in the server until stopped.

```js
var person = {
  firstName: "matt",
  lastName: "2ology",
  age: 28,
};
console.log(person);
```

In Node.js when you have a function and log it will provide the return data of that function

Any function that doesn't have an explicate `return` statement will return `undefine`

```js
function addNumber(a, b) {
  return a + b; // Explicite return statement
}
console.log(addNumber(7, 3));
// > 10

function worthless() {}
console.log(worthless());
// > undefined
```

Can assign variables to anonymous, nameless, functions. You can use anonymous function
assigned to a variable and pass that variable in other functions.

```js
var printBacon = function () {
  console.log("Bacon is healthy, don't believe the pigs!");
};

printBacon();
// > Bacon is healthy, don't believe the pigs!

setTimeout(printBacon, 5000); // Call this code in 5 seconds
// After 5 seconds
// > Bacon is healthy, don't believe the pigs!
```
