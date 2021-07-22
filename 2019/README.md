# ES2019

## Object.fromEntries()

convert a list of key-value pairs into an object

```js
const myArray = [['one', 1], ['two', 2], ['three', 3]];
const myObj = Object.fromEntries(myArray);

console.log(myObj);    // => {one: 1, two: 2, three: 3}
```

comes in handy is when working with the query string of a URL:

```js
const paramsString = 'param1=foo&param2=baz';
const searchParams = new URLSearchParams(paramsString);

Object.fromEntries(searchParams);    // => {param1: "foo", param2: "baz"}
```

## String.prototype.trimStart and String.prototype.trimEnd

`String.trim()` has been a part of the ECMAScript standard since ES5. It removes whitespace from both the beginning and the end of a string. Now we have options for removing whitespace from one side only.

```js
const str = "   string   ";

// es2019
console.log(str.trimStart());    // => "string   "
console.log(str.trimEnd());      // => "   string"

// aliases for trimLeft and trimRight (which were implemented earlier) but new naming is consistent with `String.prototype.padStart` and `String.prototype.padEnd` and therefore is preferred over the previous names
String.prototype.trimLeft === String.prototype.trimStart; // => true
String.prototype.trimRight === String.prototype.trimEnd; // => true
```

## Array.prototype.flat

enables you to easily concatenate all sub-array elements of an array

```js
const arr = ['a', 'b', ['c', 'd']];
const flattened = arr.flat();

console.log(flattened);    // => ["a", "b", "c", "d"]
```

also accepts an optional argument that specifies the number of levels a nested array should be flattened. If no argument is provided, the default value of 1 will be used

```js
const arr = [10, [20, [30]]];

console.log(arr.flat());     // => [10, 20, [30]]
console.log(arr.flat(1));    // => [10, 20, [30]]
console.log(arr.flat(2));    // => [10, 20, 30]
```

## Optional catch binding

Previously, when you wanted to use `try...catch` you had to pass in the exception as a parameter, even if you didn’t use it. Now if you don’t want to use the exception, you can use the catch block without a parameter.

```js
// Before ES2019:
try {
  // Do something.
} catch (e) {
  // Ignore the required e parameter
  // if you don't want to use it, but keep it.
}

// After ES2019:
try {
  // Do something.
} catch {
  // No need to add any parameter
}
```
