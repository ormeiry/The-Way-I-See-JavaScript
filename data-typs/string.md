# String

A string is an important data type, and we would most likely use it in every application's source code.
A string is a piece of text, and as with all data types, we would generally want to store it in a variable and work with it.
In JS, there is more than one way we can represent a string:

```js
const firstString = "With double quotes";
const secondString = "With single quotes";
const thirdString = `With backticks`; // starting from ECMAScript 2015 (a big update to JS)
```

When using double or single quotes, we need to write all of the text in the same line. If we want to start a new line we need to tell the computer that with a backslash, or we can concatenate strings.

```js
const longString =
  "This is a vary long string, we will now go to a new line by putting a backslash and pressing enter \
Now we can continue writing in the new line and it will all be stored in the same longString constant with no problems! \
This is great!.";

const secondLongString =
  "This time we will concatenate the strings" +
  "by using the + sign!" +
  "Thats all we need to do.";
```

We can use the backticks and write it all like this:

```js
const anotherLongString = `
    We open with a backtick, and now we can start typing and typing until we
    finish the string we want to store in the constant.
    This way, with the backticks, we do not have to tell the computer that this
    is the same string by using a backslash like in the example before.
`;
```

We can work with other variable and strings together:

```js
const fullName = "John Doe";
const age = 55;

const niceToMeetYou = "Hello, my name is " + fullName + ", I am " age " years old."

console.log(niceToMeetYou) // "Hello, my name is John Doe, I am 55 years old."
```

Using backticks is a cleaner way, we just use the variable name like so:

```js
const fullName = "John Doe";
const age = 55;

const niceToMeetYou = `Hello, my name is ${fullName}, I am ${age} years old`;

console.log(niceToMeetYou); // "Hello, my name is John Doe, I am 55 years old."
```

There are a lot of things we can do with strings and a lot of built-in methods for them that we can use.
