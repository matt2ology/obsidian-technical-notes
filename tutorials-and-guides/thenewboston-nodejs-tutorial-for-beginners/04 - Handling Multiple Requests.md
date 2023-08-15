# thenewboston - Node.js Tutorial for Beginners - 04 - Handling Multiple Requests

Week 31.2 | Tuesday, August 01, 2023 | 11:37 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md)

Source : https://www.youtube.com/watch?v=KsjrN-T3ZCs&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=4

When creating web apps where

1. has to deal with real time data where speed is important
2. a large volume of request

Node.js was developed for these needs.

```js
// app.js
function placeAnOrder(orderNumber){
    console.log("Customer order : ", orderNumber);

    cookAndDeliverFood(function()(
        console.log("Delivered food order");
    ));
}

// Simulate a 5 second operation
function cookAndDeliverFood(callback){
    setTimeout(callback, 5000);
}

// Simulates user web request
placeAnOrder(1)
placeAnOrder(2)
placeAnOrder(3)
placeAnOrder(4)
placeAnOrder(5)
placeAnOrder(6)
```

A `callback` is code that tells the server to be "called back" for more instructions to be
scheduled. When resources are made available or can be executed the function is then
"called back" to perform task.

Imagine a waitress waiting on other tables until "called back" to the kitchen to serve food to
their respective tables.

You can imagine that querying a database takes 5 seconds (some things just takes time) a
bunch of users try to connect to the database and instead 5 seconds for each user: we can
process all of the request at the same exact time and and then send back all of their data in
the collective 5 seconds total.

```cli
> Gets printed out
Customer order :  1
Customer order :  2
Customer order :  3
Customer order :  4
Customer order :  5
Customer order :  6

> 5 seconds later all these gets printed out
Delivered food order
Delivered food order
Delivered food order
Delivered food order
Delivered food order
Delivered food order
```
