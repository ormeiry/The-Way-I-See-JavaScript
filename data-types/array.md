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
