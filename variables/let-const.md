# Variables

So, what are those variables, and why do we need them?
Think of the very likely scenario which you will most definitely encounter while developing an app - you will have a vast amount of data that you will need to process, check, and store for future needs.
Variables are arguably the one thing a good programmer can't write applications without.

Ok, now that we know the importance of Variables, let's understand how exactly we use them in JS.

The first thing you need to do when working with variables is to declare them, and we do that using the **let**, or the **const** keywords and give them a meaningful name - the convention is to use camel case -> firstName, lastName, aVeryLongVeriableName. As you can see, the name starts with a lowercase letter, and every word after the first begins with an uppercase letter.

Let's start talking about **let**.
We use **let** when we want to declare a variable that can be changed sometime in the future:

```js
let myAge = 29;
console.log(myName); // the console will show 29
myAge = 30;
console.log(myAge); // the console will show 30
```

In the above example, we declared a variable name that holds a number (29), and we log it in the console, using the built-in console.log() -> (we will cover that later on), then we change the value of "myAge" to 30 and log it again.
Be aware that we do not use the **let** keyword again when we re-assign to 30.

By the way:

```js
// This is how we write a comment inside the code
// This will not change how the code runs in no way, shape, or form.
// The comments are only for us, and the other developers to read.
```

The other way we can use **let** is:

- Declare the name of the variable without assigning a value.
- Assign a value later on.

```js
let illAssignItLater;
illAssignItLater = true;
/*
This is a multiline comment, 
true is a boolean, it can be either - true, or false.
It is a very powerful tool in the programming world, and we will learn more about it later.
*/
```
