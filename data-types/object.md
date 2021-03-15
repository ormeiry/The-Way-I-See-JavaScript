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

<br>

We can store booleans, numbers, strings, arrays, and objects inside of an Object.
\*\*There are object methods as well. You can think of methods as functions that are properties of an object. Let's see an example:

```js
const person = {
  name: "Bob",
  age: 32,
  describe: function() {
    console.log(`This person is ${this.age} years old, and his name is ${this.name}.`)

    // 'this' is an important keyword. Here it refers to the object
    // that invokes the function.
  }
}
  person.describe(); // output: "This person is 32 years old, and his name is Bob"
}
```

We invoke the method just like we saw earlier by writing the object name and using the **"."** notation. The **this** keyword is a tricky one to understand, and I will expand on it later on.

<br>
<hr>

### Just like an Array, Objects have some built-in methods we can use. Let's take get to know some of them.

<br>

So, what if we want to loop over an object and get all the values it holds? How may we go about it?...well, we can do it in various ways. Let's see one of them now:

```js
const ourObj = {
  someKey: 'some Value',
  someKeyTwo: 'some Value Two',
  someKeyThree: 'some Value Three',
  someKeyFour: 'some Value Four',
};

// We use the Object.keys(). It returns an array of all the object keys,
// then we loop over it and access the value of each key.

Object.keys(ourObj).forEach((key) => {
  // We can chain the forEach method because its an array of keys(strings)

  console.log(ourObj[key]);
  // We take the key and use square brackets to access the value
});
```

Just like the **.** that we used earlier, we can use the square brackets, but it gives us a more dynamic way of using keys.
<br>

There is a simpler way we can get the same result we did above, and it is by using **Object.values**:

```js
const ourObj = {
  someKey: 'some Value',
  someKeyTwo: 'some Value Two',
  someKeyThree: 'some Value Three',
  someKeyFour: 'some Value Four',
};

// The Object.values() returns an array of all the object values,
// then we loop over it and can do what we need.

Object.values(ourObj).forEach((value) => {
  // We can chain the forEach method because its an array
  console.log(value);
});
```
