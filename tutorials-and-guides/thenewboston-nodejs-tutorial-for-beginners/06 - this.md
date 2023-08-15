# Node.js Tutorial for Beginners - 06 - `this`

Week 31.3 | Wednesday, August 02, 2023 | 11:44 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md)

Source : https://www.youtube.com/watch?v=uiZxziF4Ol8&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=6

When you see the keyword `this` refers to the object that called it

```js
var Bucky = {
  printFirstName: function () {
    console.log("My name is Bucky");
    console.log(this === Bucky); // `this` refers to what is calling it
  },
};
Bucky.printFirstName(); // `printFirstName()` is what's calling `this`
// > My name is Bucky
// > true
```

## What happens when we make a function that isn't clearly part of any object?

The default calling context is global: your main program (`global`) will call it.

When a function is made, but does not belong to any object it is `global`

```js
var Bucky = {
  printFirstName: function () {
    console.log("My name is Bucky");
    console.log(this === Bucky);
  },
};
Bucky.printFirstName();
// > My name is Bucky
// > true

function doSomethingWorthless() {
  console.log("\nMy name is Boruto Uzumaki");
  console.log(this === global); // `this` refers to the whole entire program
}
doSomethingWorthless();
// > My name is Boruto Uzumaki
// > true
```
