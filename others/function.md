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

<br>
Arrow function sometimes looks cleaner, and they have their use cases.
There are some differences between normal functions and arrow functions, and we will learn about them later on.
