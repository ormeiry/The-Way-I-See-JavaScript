# Array

Arrays are one of the most commonly used data types.
We can think of arrays as a container of multiple variables.
In JS, arrays are flexibles. We don't need to specify the length when creating a new Array, unlike we do in other strong-typed programming languages. In addition to all that, we can store a mix of data types.

```js
const ourFirstArray = ['a string', true, 10, 'another string!'];
// Now we have an array with 4 variables inside it.
// Arrays are zero-based, so the first item inside it is at position 0.

// The way we can access item is by using [ ] and the index we want.
console.log(ourFirstArray[0]); // output: "a string"
console.log(ourFirstArray[2]); // output: 10
```

Just like we learned on strings, the array object has a length property, which we can use to get the total length of the array, or in other words, the number of items it stores.

```js
// We create an array with five numbers.
const ourArray = [1, 29, 42, 13, 12];

console.log(ourArray.length) output: 5
// This is will be useful in cases in which we need to take some action
// according to the length of the array in hand.
```

## Let's see some of the main methods the array object has:

<br />

**array.concat()**

```js
// We use this method in order to take the original array, and add to it.
// This method returns a brand new array without mutating the old one

const ogArr = ['this', 'will', 'not', 'change!'];
const otherArr = ['Will', 'I', 'join the new array?', true];

const joinedArr = ogArr.concat(otherArr);

// Unchanged
console.log(ogArr);
output: ['this', 'will', 'not', 'change!'];
console.log(otherArr);
output: ['Will', 'I', 'join the new array?', true];

// New array
console.log(joinedArr);
output: [
  'this',
  'will',
  'not',
  'change!',
  'Will',
  'I',
  'join the new array?',
  true,
];
```
