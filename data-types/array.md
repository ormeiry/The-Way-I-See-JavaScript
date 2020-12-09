# Array

Arrays are one of the most commonly used data types.
We can think of an array as a container of multiple variables.
In JS, arrays are flexibles. We don't need to specify the length when creating a new array, unlike we do in other strong-typed programming languages. In addition to all that, we can store a mix of data types.

```js
const ourFirstArray = ['a string', true, 10, 'another string!'];
// Now we have an array with 4 variables inside it.
// Arrays are zero-based, so the first item inside it is at position 0.

// The way we can access an item is by using [ ] and the index we want.
console.log(ourFirstArray[0]); // output: "a string"
console.log(ourFirstArray[2]); // output: 10
```

<br />
<br />

Just like we learned on strings, the array object has a length property, which we can use to get the total length of the array, or in other words, the number of items it stores.

```js
// We create an array with five numbers.
const ourArray = [1, 29, 42, 13, 12];

console.log(ourArray.length) output: 5
// This will be useful in cases in which we need to take some action
// according to the length of the array in hand.
```

We can add and replace items in the array by assigning them to an index directly.

```js
const arr = [1, 10, -2, 26];

arr[2] = "I've Changed!";
console.log(arr);
output: [1, 10, "I've Changed!", 26];

// Add an item to the end of the list manually by using the length
// property, it will give us the length of the array which is 4, and we
// use it as an index. as you remember, arrays
// index start at 0, so with 4 items we reached index 3.
// 4 will be a new index.

arr[arr.length] = "I'm Last!";
output: [1, 10, "I've Changed!", 26, "I'm Last"];
```

<hr><br>

## Let's see some of the main methods the array object has:

<hr><br>

**array.push()**

```js
// This method will add the item we pass to it to the end of the array.
const arr = ['hello', 'hi'];
arr.push('Hey');

console.log(arr); // output: ["hello", "hi", "Hey"]
```

**array.pop()**

```js
// As a counter to the push method, this one will remove the
// last item in the array. We don't need to give it any arguments.

const arr = ['hello', 'hi', 'Hey'];
arr.pop();

console.log(arr); // output: ["hello", "hi"]
```

**array.shift()**

```js
// Now that we know how to remove the last item,
// this is how to remove the first one.

const arr = [4, 6, 19, 20];

// It returns the item it removes, so we can store it.
let firstItem = arr.shift();
console.log(firstItem);
output: 4;

// The second item (6), is now the first one as the whole
// array shifts one spot back.

firstItem = arr.shift();
console.log(firstItem);
output: 6;
```

**array.unshift()**

```js
// If we want to add an item to the start of the array,
// we can use unshift method.

const arr = ['I will move to index 1', 'I will move to index 2'];
arr.unshift("I'm first!");

console.log(arr);
// output:  ["I'm first!", "I will move to index 1", "I will move to index 2"]
```

**array.concat()**

```js
// We use this method in order to take the original array content, and add to it.
// This method returns a brand new array without mutating the original one.

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

**array.some()**

```js
// Let's say we want to check if our array has some
// item that answers a condition.
// We want to know if the array contains a number larger than 20.

const numArr = [20, 19, 26, 10, 12];
// We call the --some-- method, and pass a function that runs for
// each item in the array, inside that function we get access to
// the current item, the index of that item, and the array itself.

numArr.some(function (item, index, ourArray) {
  // now that we are inside the function body, for each
  // item we will check if the item is larger than 20 with the > sign.
  return item > 20;
});
// returns true.
// This will return true if even only one of the items is larger than 20.

const otherNumArr = [2, 19, 6, 11, 17];
otherNumArr.some(function (item, index, ourArray) {
  return item > 20;
});
// returns false
```
