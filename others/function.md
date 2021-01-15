# Function

A function is a piece of code that we write when we need some task done. We can write a function that accepts some parameters, checks things, performs actions, and returns a value.
<br>

### We can write a function declaration:

```js
function ourFuncNam(/* parameters goes here */) {
  // code goes here
  return; // something
}

// call the function
ourFuncNam(/* pass arguments here */);
```

### We can also use a function expression:

```js
const ourFuncNam = function (/* same */) {
  // same as above
};
```

<br>

Say we need a function to take any number and return that number times 10.

```js
function timesTen(num) {
  return num * 10;
}

// now, we can call that function and pass a num to it.
// it will always provide the same outcome (the num times 10).
// it is useful and predictable!.

// we can store the returned value:
const valOne = timesTen(1);
const valTwo = timesTen(12);
const valThree = timesTen(8);

console.log(valOne, valTwo, valThree);
// output: 10, 120, 80
```

<br>

### Another way (on modern js) of writing a function is using an Arrow Function, syntax:

```js
const ourArrowFunc = (num) => {
  return num * 10;
};

// if the function has one line inside its body, we can write it like so:

const ourSecArrowFunc = (num) => num * 10;
```

### A function does not always have to return something, it can do a task and that's it.

```js
const myFirstName = 'John';
const myLastName = 'Doe';

const sayHi = (firstName, lastName) =>
  console.log(`Hello ${firstName} ${lastName}!`);

sayHi(myFirstName, myLastName);
// output: Hello John Doe!

// If we try to store the value returned like in the example
// above, we will get undefined as the value.

const noReturnInFunc = sayHi(myFirstName, myLastName);
console.log(noReturnInFunc);
// output: undefined
```

<br>

Arrow function sometimes looks cleaner, and they have their use cases.
There are some differences between normal functions and arrow functions, and we will learn about them later on.

<br>

### Before we continue this section, let's try to break down the core functionality of a function (pun not intended).

- It can return a value, we can store it in a variable and use it.
- It can take parameters, and we pass them as arguments when invoking the function.
- It is used for cases when we want some predicted behavior to run over and over again (take a num and always return it times 10).
- It gives us the power to not repeat lines of code (follow the rule of "Do not repeat yourself).
