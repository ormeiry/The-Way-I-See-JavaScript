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

As you can see, the **shoppingList** holds the key-value pairs inside and we use them with the "." after the **shoppingList**. Wine is a nested object that holds its own key-value pairs. We get them by using the **"."** one more time -> **shoppingList** -> then the **"."** to get a reference to the **wine** -> then another **"."** to get a reference to the keys inside it. If we try to get a value inside an object by using a key that does not exist, we get back **undefined**.

<br>

So I guess you are starting to see where Objects can be of help.
In some applications, for example, we need to collect some User data from the client, maybe via an HTML form, and send it to our backend server for it to save the data to some database. We need a data structure to hold the User data while we are collecting it - that is where the JS Object shines.
