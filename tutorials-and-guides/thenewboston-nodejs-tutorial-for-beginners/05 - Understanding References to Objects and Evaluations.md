# Node.js Tutorial for Beginners - 05 - Understanding References to Objects

Week 31.3 | Wednesday, August 02, 2023 | 11:24 PM

Related : 

Source : https://www.youtube.com/watch?v=kNHrHSTYs1U&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=5

## Everything is a reference

In Node.js everything is a reference. `Person` is a reference to `Bucky` and so when you change
`Person`'s `favFood` you reassign `Bucky`'s `favFood`

```js
var Bucky = {
    favFood: "bacon",
    favMovie: "5 Centimeters per Second"
};

var Person = Buckey;

Person.favFood = "salad";
console.log(Buckey.favFood);
// > salad
```

## Evaluation: the difference between two and three equal signs (`==` and `===`)

```js
console.log(19 == "19"); // > True (compares the values)
console.log(19 === "19"); // > False (compares the values and types)
```
