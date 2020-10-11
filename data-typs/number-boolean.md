# Data Types

We have met some of the data types on the variables section, now let's get to know them better.

In programming, and in JS as part of the programming world, data types are the way we tell the computer how to handle the information. I'll try to explain them in the easiest way possible, let's begin.

We need to tell the computer that a variable is of type **string**, **number**, **boolean**, **object**, **array**, etc, in order for it to handle, process, and
store it in memory the right way.

When we use numbers we can do these things for example:

```js
let myNum = 5;
myNum = myNum + 5; // we add 5 to our number, now it's 10.

myNum = myNum - 2; // now it's 8.
myNum = myNum * 3; // now it's 24.
myNum = myNum / 2; // not it's 12.

// we can shorten it
myNum += 2; //now it's 14.
myNum % 6; // give us the remainder, now our number is 2.
myNum++; // increment by 1, now it's 3.
myNum--; // decrement by 1, it's 2 again.
myNum *= 0.2; // now it's 0.4.

/* 
in JS we can hold a floating number as well as an integer. 2.0 and 2 are the same here.  
In C# for example we need to declare:
int myFirstNum = 10;
float myOtherNum = 10.0;

No need for that here.
*/
```

We can also concatenate numbers and text:

```js
let whatAmI; // currently -undefined- (also a type).
whatAmI = 5 + '5'; //  it's now a string "55".
```

Another data type is a boolean, we as programmers use booleans to control our flow of the code, determine whether or not to activate something, is a user authenticated, is something being loaded and we need to display a loading spinner, and much more...

```js
let isDataReady = false;

function getData() {
  // our first function! we will get to how it works later in more detail.

  // fetching data from the web . . .
  // data recivied!!

  isDataReady = true;
  // return data
}

/* 
the function is just declared, we will need to call it for it to run the code inside.
now let's see how it works and why we use it.
*/

if (isDataReady === false) {
  /*
this is an if check, we check if our variable is equal to false with ===.
if the expression is correct, we will get inside this block, and the code inside the { } will execute.
isDataReady is still false because we didn't call the function yet.
*/

  // now we call the function and invoke it.
  getData();
  /* 
the code inside the function runs and set isDataReady to be true.
*/
}

// we check again for some other reason...
if (isDataReady === false) {
  // the expression is not correct!
  // now we skip this part of the code!
}

// do some other code!
```

Another example:

```js
const user = {
  name: 'John Doe',
  age: 30,
  isAuthenticated: false,
  id: '12345',
};

/* 
the user above is trying to get inside a section in our website that is for authenticated personal only,
in our code, we write a check for these scenarios in advance.
*/

function checkAuth(user) {
  if (user.isAuthenticated === false) {
    return "Sorry, you can't go in here";
  } else {
    // this else block will work if the if one will not
    return 'Welcome!!';
  }
}
```

The example above is a simple one, in real applications, the process is somewhat different and has more levels and complexity.
