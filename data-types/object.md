# Object

Objects in JS are everywhere. The Array's, Functions, classes and more, were built using the JS object. An object is like a box where we put some key-value pairs. The object has a **Pass by reference** behavior just like an Array.

Let's take a look at a simple example:

```js
// We create a variable and set it equal to {}
const shoppingList = {
  // key: value pairs separated by commas
  apples: 5,
  bananas: 10,
  grapes: 7,
  wine: {
    // nested object
    red: 2,
    white: 1,
  },
  water: 6,
  isFinished: false
  whosTurnToGo: "Bob",
};

// We now have a shopping list with some ingredients as keys and an amount as value.

console.log(shoppingList.grapes); // output: 7
console.log(shoppingList.water); // output: 6
console.log(shoppingList.wine.red); // output: 2
console.log(shoppingList.wine.white); // output: 1
console.log(shoppingList.someNoneExistingKey); // output: undefined
```
