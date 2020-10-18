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

When we create a String in the JS language, it is automatically converted between **string primitives**, which we have seen until now, and **String objects**, and for that reason, we can call any of the helper methods of the String object on a string primitive.

```js
const strObj = new String("This is how we create a string object directly");
// as you can see, we are using a new syntax here to create some object
// don't worry we will get to that later.
```

You can think of the **String object** in the same way we look at humans.
humans are not all the same, as not all strings are the same, but all humans share some things, in the sense that we all have eyes, ears, hands, the ability to speak and make noises, and much more. (I'm referring to healthy humans, no disrespect to others)
So, any string we create has some abilities and properties that it is "born" with.

There are a lot of things we can do with strings and a lot of built-in methods for them that we can use. Let's see some of them in action:

```js
const myStr = "How long am I??";
console.log(myStr.length); // outputs 15
// gives us the length of the string, the number of characters and spaces it has.
```

```js
const myStr = "What index am I??";
console.log(myStr.charAt(5)); // outputs ' i '
console.log(myStr.charAt(0)); // outputs ' W '
console.log(myStr.charAt(myStr.length - 1)); // outputs ' ? '
// charAt() is a method that returns the character from the specified index.
// Characters in a string are indexed from left to right.
// Starts at position 0 and ends at position (myStr.length - 1).
```
