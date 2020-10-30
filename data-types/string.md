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

const niceToMeetYou =
  "Hello, my name is " + fullName + ", I am " + age + " years old.";

console.log(niceToMeetYou); // "Hello, my name is John Doe, I am 55 years old."
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

You can think of the String object in the same way we think about cars. Cars are not all the same, as not all strings are the same, but all the cars share some things, in the sense that all (working) cars can start, can play music, have windshields, have an engine, can break, and much more. So, any string we create has some abilities and properties that the **String object** inherently provides.
There are a lot of things we can do with strings and a lot of built-in methods for them that we can use. Let's see some of them in action:

**string.length**

```js
// gives us the length of the string, the number of characters and spaces it has.

const myStr = "How long am I??";
console.log(myStr.length); // outputs 15
```

**string.charAt()**

```js
// charAt() is a method that returns the character from the specified index.
// Characters in a string are indexed from left to right.
// Starts at position 0 and ends at position (myStr.length - 1).

const myStr = "What index am I??";
console.log(myStr.charAt(5)); // outputs ' i '
console.log(myStr.charAt(0)); // outputs ' W '
console.log(myStr.charAt(myStr.length - 1)); // outputs ' ? '
```

**string.concat()**

```js
// The concat() method returns a new string.
// The result will be the two strings combined.

let strOne = "I was here first!, ";
let strTwo = "I want to be added!";
const newStr = strOne.concat(strTwo);

console.log(newStr); // output: "I was here first!, I want to be added!";
```

**string.indexOf()**

```js
// Returns the index of the first occurrence of the specified value
// Starting the search at the index we specify (if we do not, the default is 0)
// If the exact value does not exist in the string, it will return -1.

const searchMeStr = "Can you find something here??";

let indexOfValue = searchMeStr.indexOf("you", 5);
console.log(indexOfValue); // output: -1
// We asked the method to start searching at index 5
// There is no match since "you" starts at index 4.

indexOfValue = searchMeStr.indexOf("you");
console.log(indexOfValue); // output: 4
// This time we didn't add the index to start with
// The default is 0, and the method will return the index 4.
```

**string.lastIndexOf()**

```js
// This method works the same as the above one, but as implied in its name
// it will return the index of the value we search inside the string, but where it is last appearing.

const findTheLast = "This string is a special string!!";

let lastAppearanceAt = findTheLast.lastIndexOf("string");
console.log(lastAppearanceAt); // output: 25
```

**string.split()**

```js
// This method splits a String object into an array of strings by separating the string into substrings.
// We aill learn about array later on, for now, think of it as a stack of data,
// it looks like [1, 2, 3, 4] -> it's starts at 0 index just like a string
// we can store any data type at each slot of the array.

const stringToSplit = "This string will be split into an array of strings!";

// we need to tell the split method what we want to split the string by.
// here we tell the split to split the string by spaces.
const newStrArray = stringToSplit.split(" ");

console.log(newStrArray);
// output: ["This", "string", "will", "be", "split", "into", "an", "array", "of","strings!"]

// we can tell the method to stop at some point, maybe we want 5 items in // the array and not all items as we have seen above?...

const shortStrArr = stringToSplit(" ", 5);

console.log(shortStrArray);
// output: ["This", "string", "will", "be", "split"]
```

**string.toLowerCase()**

```js
// This method returns the value of the string but converts it all to lower case

const str = "This string will be changed to LOWERcase only. ";

console.log(str.toLowerCase());
// output: this string will be changed to lower case only.
```

**string.toUpperCase()**

```js
// This method returns the value of the string but converts it all to upper case

const str = "This string will be changed to UPPERcase only. ";

console.log(str.toUpperCase());
// output: THIS STRING WILL BE CHANGED TO UPPERCASE ONLY.
```

**string.substring()**

```js
// This method returns a section of a string as a new string.
// We need to pass as a parameter An integer between 0 and
// ( string.length() - 1 ), to tell the method where to start "cutting".

const ourStr = "Now you will see the magic!.";
const ourSubStr = ourStr.substring(13);
console.log(ourSubStr); // output: see the magic!.

// We can add an optional second parameter to tell the method
// where to stop "cutting" the string. if we don't add it, it goes all
// the way to the end, just like the above example.

const ourSecondSubStr = ourStr.substring(13, 16);
// 16 is where we want to stop, it is not included in the returned string.
console.log(ourSecondSubStr); // output: see
```
