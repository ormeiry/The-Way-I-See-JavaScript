# Array

Arrays are one of the most commonly used data types.
We can think of an array as a container of multiple variables.
In JS, arrays are flexibles. We don't need to specify the length when creating a new array, unlike we do in other strong-typed programming languages. In addition to all that, we can store a mix of data types.

```js
const ourFirstArray = ['a string', true, 10, 'another string!'];
// Now we have an array with 4 variables inside of it.
// Arrays are zero-based, so the first item inside of it is at position 0.

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
// output: [1, 10, "I've Changed!", 26];
```

Add an item to the end of the list manually by using the length property, it will give us the length of the array which is 4, and we
use it as an index. as you remember, arrays
index start at 0, so with 4 items we reached index 3.
4 will be a new index.

```js
arr[arr.length] = "I'm Last!";
// output: [1, 10, "I've Changed!", 26, "I'm Last"];
```

### **Array.isArray()**

If we want to check if some data is an array, we can use this Array method like so:

```js
const str = "I'm not an array";
const num = 15;
const arr = ['this', 'will', 'return', 'true'];

// It will return false if the value passed to it is not an array, and true if it is.
console.log(Array.isArray(str)); // output: false
console.log(Array.isArray(num)); // output: false
console.log(Array.isArray(arr)); // output: true
```

<hr><br>

## Let's see some of the main methods the array object has:

<br>

### **array.push()**

This method will add the item we pass to it to the end of the array.

```js
const arr = ['hello', 'hi'];
arr.push('Hey');

console.log(arr); // output: ["hello", "hi", "Hey"]
```

<br>

### **array.pop()**

As a counter to the push method, this one will remove the
last item in the array. We don't need to give it any arguments.

```js
const arr = ['hello', 'hi', 'Hey'];
arr.pop();

console.log(arr); // output: ["hello", "hi"]
```

<br>

### **array.shift()**

Now that we know how to remove the last item,
this is how to remove the first one.

```js
const arr = [4, 6, 19, 20];

// It returns the item it removes, so we can store it.
let firstItem = arr.shift();
console.log(firstItem);
// output: 4;

// The second item (6), is now the first one as the whole
// array shifts one spot back.

firstItem = arr.shift();
console.log(firstItem);
// output: 6;
```

<br>

### **array.unshift()**

If we want to add an item to the start of the array,
we can use unshift method.

```js
const arr = ['I will move to index 1', 'I will move to index 2'];
arr.unshift("I'm first!");

console.log(arr);
// output:  ["I'm first!", "I will move to index 1", "I will move to index 2"]
```

<br>

### **array.concat()**

We use this method in order to take the original array content, and add to it.
This method returns a brand new array without mutating the original one.

```js

const ogArr = ['this', 'will', 'not', 'change!'];
const otherArr = ['Will', 'I', 'join the new array?', true];

const joinedArr = ogArr.concat(otherArr);

// Unchanged
console.log(ogArr);
// output: ['this', 'will', 'not', 'change!'];
console.log(otherArr);
// output: ['Will', 'I', 'join the new array?', true];

// New array
console.log(joinedArr);
// output: [
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

<br>

### **array.some()**

Let's say we want to check if our array has some item that answers a condition.
We want to know if the array contains a number larger than 20.
<br>

We call the **some** method, and pass a function that runs for
each item in the array, inside that function we get access to
the current item, the index of that item, and the array itself.

```js
const numArr = [20, 19, 26, 10, 12];

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

<br>

### **array.every()**

Just like in the **some** method above, this method checks the values
inside the array, and returns a boolean. The difference is, that the
**every** method returns true only if all the values answer the condition

```js
const numArr = [20, 2, 11, 130, 18];
numArr.every(function (item, index, ourArray) {
  return item >= 10;
}); // This returns false! the 2 inside the array is less than 10

const otherNumArr = [17, 32, 18, 1250, 25];
otherNumArr.every(function (item, index, ourArray) {
  return item >= 10;
}); // This return true!
```

<br>

### **array.filter()**

As the name suggests, this method filters an array,
and returns the new array containing only the items
that passed the given "test".

```js
const initialArr = [2, 3, 5, 10, 4, 1];
// now we create a new constant to hold the result.

const filteredArr = initialArr.filter(function(item, index, ourArray) {
	// Let's filter out the items that are smaller than their index.
	// Remember, we run this function and have access to each
	// item and its index, so the first item will be 2 with the index of 0
	// the second item is 3 with the index of 1, and so on.
	return item > index
}
console.log(filteredArr); // output: [2, 3, 5, 10]

// The initialArr stays the same as it was.
```

<br>

### **array.map()**

The **map** method is used to create a new array
out of the original one. We can perform an action on
each of the array items when iterating through them.
<br>

The method returns a new array containing the results
of our actions.

```js
const ogArr = [1, 2, 3, 4, 5, 6];

const newArr = ogArr.map(function (item, index, ourArray) {
  // Every item in the array will be multiplied by 3
  // and then will be pushed to the new array.
  return item * 3;
});

console.log(newArr); // output:  [3, 6, 9, 12, 15, 18]

// The original array stays as it was.
console.log(ogArr); // output:  [1, 2, 3, 4, 5, 6]
```

<br>

### **array.slice()**

We use the slice method to get a copy of an array.
We tell the method where to start slicing and
where to stop, the end will not be included.

```js
const ogArr = ['hi', 'hello', 'hey', 'hola'];

const copyArr = ogArr.slice(0, 2);
// the numbers are the index.
console.log(copyArr);
// output: ["hi", "hello"]
```

If we pass only 1 number to the method, it will slice from that index to the end of the array.

```js
const otherCopyArr = ogArr.slice(1);
console.log(otherCopyArr);
// output: ["hello", "hey", "hola"]
```

If we want a copy of the whole array, we
call the method, with no arguments.

```js
const fullCopyArr = ogArr.slice();
// output: ["hi", "hello", "hey", "hola"]

// The original array remains unchanged.
```

<br>

### **array.reverse()**

As the name suggests, we use this method to
reverse the order of the items inside the array.

```js
const ourArr = [10, 20, 'Hello', true, 30];

console.log(ourArr.reverse());
// output: [30, true, "Hello", 20, 10]
```

This method will change the original array.
If we want a new reversed array, we
can use the slice method, and chain the reverse method.

```js
const ogArr = [1, 2, 3, 4, 5];

const newReversedArr = ogArr.slice().reverse();
console.log(newReversedArr);
// output: [5, 4, 3, 2, 1]

console.log(ogArr);
// output: [1, 2, 3, 4, 5]
```

<br>

### **array.find()**

We will use this method to find one item, the first
item in the array that answers the condition we test.

```js
const arr = ['hello', 'my', 'name', 'is', 'John', 'Doe'];

const foundItem = arr.find(function (item, index, ourArr) {
  // As in most of the methods we have seen before,
  // on each iteration we get access to the item,
  // its index and the array itself.

  let itemLength = item.length;
  // We get the strings length
  // if it's 2, the expression below will be true
  // and the current item will be stored in the --foundItem--.
  return itemLength === 2;
});
```

It is important to understand that unlike the
**filter** method, we don't get an array of
all the matching items. As soon as the **find**
method finds an item that fits, it stops immediately
and returns it and only it. The "is" inside the array
also meets the condition but will be never reached.
<br>

### **array.reduce**

The **reduce** method takes one function that runs like so:

- A function with 4 arguments
  - **accumulator:**
    <br>
    The sum or result of the method when adding all the array items one at a time.
  - **currentValue:**
    <br>
    The current item in the array that is looped over at the moment.
  - **currentIndex:**
    <br>
    The current index that is looped over.
  - **array:**
    <br>
    The original array.

<br>
And one optional argument, that is the initial value.

The returned value after all this is the accumulated value at the end.

It's hard to understand without an example, so let's take a look at a simple one.

```js
const arr = [1, 2, 3, 4, 5, 6];

// arr.reduce(function, initialValue)
const sumOfArr = arr.reduce(function (
  accumulator,
  currentValue,
  currentIndex,
  array
) {
  // We run a function with the arguments we talked about above.

  // For each item in the array we take its value (currentValue)
  // and add to the total sum (accumulator).
  return accumulator + currentValue;
},
0);
// The second argument to the method is the initial value we want to start with, in this case it's 0.

console.log(sumOfArr);
// output: 21
```

Ok, let's try to break it down:

- We give an initial value of 0, this value will be the accumulator for the first time the function runs.
- The function runs for the first index and it gets the currentValue (1)
- We return then -> 0 + 1. Now the accumulator = 1.
- The function now runs for the second time and on index 1, currentValue = 2.
- We again return accumulator + currentValue -> 1 + 2. accumulator = 3.
- Function runs for the third item, currentValue = 3.
- We again return accumulator + currentValue -> 3 + 3. accumulator = 6.

All the way to the end of the array -> 6 + 4 -> 10 + 5 -> 15 + 6.
So at the end of it all, the **sumOfArr** holds the value 21.

**We can do so much more with this method, we will definitely see more of it later on.**
