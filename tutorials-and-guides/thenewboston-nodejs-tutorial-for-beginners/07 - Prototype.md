# Node.js Tutorial for Beginners - 07 - Prototype

Week 31.4 | Thursday, August 03, 2023 | 12:12 AM

Related :

Source : https://www.youtube.com/watch?v=IW2M8G8uJ6o&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=7

Prototyping give the ability to add methods or properties to objects and classes.

Recall that the `this` keyword refers to whatever object is calling it and allows one to have
any number of instances with whatever different attributes.

```js
function User() {
  this.name = "";
  this.life = 100;
  this.giveLife = function giveLife(targetPlayer) {
    targetPlayer.life += 1;
    console.log(this.name + " gave 1 life to target " + targetPlayer.name);
  };
}

var Bucky = new User();
var Wendy = new User();
Bucky.name = "Bucky";
Wendy.name = "Wendy";

Bucky.giveLife(Wendy);
console.log("Bucky: " + Bucky.life);
console.log("Wendy: " + Wendy.life);

// You can add functions to all objects
User.prototype.uppercut = function uppercut(targetPlayer) {
  targetPlayer.life -= 1;
  console.log(this.name + " uppercutted " + targetPlayer.name);
};

Wendy.uppercut(Bucky);
console.log("Bucky: " + Bucky.life);
console.log("Wendy: " + Wendy.life);

// You can add properties to all objects
User.prototype.magic = 60;
console.log(Bucky.magic);
console.log(Wendy.magic);
```
