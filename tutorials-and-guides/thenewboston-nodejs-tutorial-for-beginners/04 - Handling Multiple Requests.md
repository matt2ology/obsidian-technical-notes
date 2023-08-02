# thenewboston - Node.js Tutorial for Beginners - 04 - Handling Multiple Requests

Week 31.2 | Tuesday, August 01, 2023 | 11:37 PM

Related : 

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

A `callback` is code that tells the server to be "called back" for more instructions to be scheduled.

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
