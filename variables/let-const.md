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
**true** is a boolean, it can be either - **true**, or **false**.
It is a very powerful tool in the programming world, and we will learn more about it later.
*/
```

When using **let**, we can not only re-assign the value of the variable, but we can also give it a different data type (more on data types on a separate file later on).

```js
let imGoingToChangeTypes = 10;
imGoingToChangeTypes = "I was a number a second ago, now I'm a string of text!";
imGoingToChangeTypes = false; // Now I'm a boolean!
```

As you can see in the example above, we need to be very careful when using **let**.  
We can accidentally change a type when dealing with large codebases, and it can break our application!.

Ok, so these are the basics of **let**, what about **const**?

The **const** keyword is used to store a variable just like **let**, with some differences:

- const cannot be declared without assigning a value straight away.

```js
const someValue;
someValue = "This is a string! we will learn all about it!"
// this code will not work, it will give us an error.
```

```js
const someValue = "Hello!";
// this is good, it will work.
```

As you can see in the examples above, it works differently than **let**.

- One more difference between **let** and **const** is that **const**, once assigned a value, it cannot be changed.

```js
const tryToChangeMeLater = 10;
console.log(tryToChangeMeLater); // outputs 10

tryToChangeMeLater = 15;
// this will give us an error, we cannot change a value of a constant.
```

There are some cases we can change something stored inside a constant:

```js
const ourFirstObject = {
  firstName: "John",
  lastName: "Doe",
};

ourFirstObject.firstName = "NOT John!!";
```

In the example above we see our first JS object, we will learn all about it in a separate file. All you need to understand now is that the object has properties(it's like a container of values), and we are allowed to change the properties themselves. even when using **const**.
What is happening is, we are not changing the object itself to be some new object, we change the object's properties with the **.** after the object name (we will learn more about it).

```js
const someObj = {
	firstName: "Name"
}

someObj = {
	firstName = "Other Name"
}
 // This will fail, in this example, we are trying to change the object directly, we are re-assigning the constant **someObj** itself.
```
