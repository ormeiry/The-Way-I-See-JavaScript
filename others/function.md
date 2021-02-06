# Function

A function is a piece of code that we write when we need some task done. We can write a function that accepts some parameters, checks things, performs actions, and returns a value. In the JS world, functions are one of the most important things to master.
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

### Another way (modern js) of writing a function is using an Arrow Function, syntax:

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

### Before we continue this section, let's try to break down the core functionality of a function. (pun not intended)

- It can return a value that we can store in a variable and use it.
- It can take parameters, and we pass them as arguments when invoking the function.
- It is used for cases when we want some predicted behavior to run over and over again. (take a num and always return it times 10)
- It gives us the power of not repeating lines of code. (we follow the rule of "Do not repeat yourself")

<br>

Ok, so now we had the chance to see functions in action, but the examples we have seen are too simple, it's hard to understand the power of functions without some real-world examples. Let's try and create a "real world function".

<br>

Say we have a webpage, and we want to add a listener to whenever a user clicks on a button.

### index.html

```html
<html>
  <body>
    <h1>Click The Button!</h1>
    <button id="btn">If You Click I Will Say Hello!</button>

    <script src="./ourJsFileName.js"></script>
  </body>
</html>
```

### ourJsFileName.js

```js
// We select the button from our HTML using its id
// and store it in a variable.

const btn = document.querySelector('#btn');
// for ID, we use the # sign and the id name we gave to the element.

// We create the function
const sayHello = () => {
  alert('Hello!!!');
};

// We add the event listener, saying we are listening
// for a click on the button, and we want to envoke the
// sayHello function when the event takes place.
btn.addEventListener('click', sayHello);
```

So, you might be thinking, OK... functions are nice, but do I have to use them?.
In most cases where we create a helper function, we don't **have to**, but it will be bad not to.

Let's look at this example:

```js
const user = {
  name: 'Bob',
  age: 22,
  otherData: [{ email: 'BOB@Bobson.com' }, { phoneNumber: '111-111-222-2222' }],
};

if (user.age > 18) {
  const response = someApiCall(user.otherData);
  if (response.isApiCheckWasOk) {
    alert(`Hi ${user.name}, The test was ok, keep going.`);
  } else {
    alert(`Hi ${user.name}, something went wrong.`);
  }
} else {
  alert('Must be over 18');
}

// Now, if we had another user, we had to write the whole thing all over again and fix it for that said user.

const userTwo = {
  name: 'John',
  age: 50,
  otherData: [
    { email: 'John@johnson.com' },
    { phoneNumber: '111-111-555-7777' },
  ],
};

if (userTwo.age > 18) {
  const response = someApiCall(userTwo.otherData);
  if (response.isApiCheckWasOk) {
    alert(`Hi ${userTwo.name}, The test was ok, keep going.`);
  } else {
    alert(`Hi ${userTwo.name}, something went wrong.`);
  }
} else {
  alert('Must be over 18');
}

// well, if it's just these two, I guess it's fine(not really).
// What if we had 100 users?. That's why we write functions.
```

The function will look this:

```js
function makeApiCallIfAgeIsOk(userObj) {
  if (userObj.age > 18) {
    const response = someApiCall(userObj.otherData);
    if (response.isApiCheckWasOk) {
      alert(`Hi ${userObj.name}, The test was ok, keep going.`);
    } else {
      alert(`Hi ${userObj.name}, something went wrong.`);
    }
  } else {
    alert('Must be over 18');
  }
}

// Now, we only have to invoke the function and pass the user we want.

makeApiCallIfAgeIsOk(user);
makeApiCallIfAgeIsOk(userTwo);
// makeApiCallIfAgeIsOk(userThree)
// makeApiCallIfAgeIsOk(userfour)
// makeApiCallIfAgeIsOk(userFive)
// makeApiCallIfAgeIsOk(userSix)
```

I know this example is not so realistic, but I believe you got the idea.
