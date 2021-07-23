# ES2017

## Object.values()

```js
const myObj = {one: 1, two: 2, three: 3};

console.log(Object.values(myObj)); // → [1, 2, 3]
```

## Object.entries()

takes an object as an argument and returns an array of the object’s own enumerable string-keyed property pairs in the form of `[key, value]`

```js
const myObj = {one: 1, two: 2, three: 3};

console.log(Object.entries(myObj));
// [["one", 1], ["two", 2], ["three", 3]]
```

## `String.prototype.padStart` and `String.prototype.padEnd`

```js
// Add characters at the beginning until the string reaches length of n characters.
'Hello'.padStart(9, '-') // → '----Hello'

// second parameter is optional and defaults to empty space character
'Hello'.padStart(9) // → '    Hello'

// if string is already beyond this length, nothing will happen
'Hello'.padStart(3) // → 'Hello'
```

## async functions

```js
async function getCurrencies() {
  // Use fetch to get data from API
  // and assign it to a variable:
  const data = await fetch('https://currencyapi.net/api/v1/rates?key=7zq3xkh2qeZcnvFhfyDyFlvqx4EmQ7R3N1qq')
  // Convert the response to JSON
  // and assign it to a variable:
  const json = await data.json()

  // Log the JSON to console:
  console.log(json);
}
```

as opposed to using a `Promise`

```js
fetch('https://currencyapi.net/api/v1/rates?key=7zq3xkh2qeZcnvFhfyDyFlvqx4EmQ7R3N1qq')
  // Convert the response to JSON:
  .then(res => res.json())
  // Log the JSON to console:
  .then(data => console.log(data))
  // Log any errors:
  .catch(err => console.log(err))
```

## Trailing commas

Makes dealing with version control easier:

Can be used with function parameters, array items, and objects properties.

```js
// Before adding new parameter:
function myFunc(
  parOne,
  parTwo,
  parThree
) {}

// Before adding new parameter:
function myFunc(
  parOne,
  parTwo,
  parThree, // First change: new ",".
  parFour // Second change: new parameter.
) {}


// With trailing comma:
// Before adding new parameter:
function myFunc(
  parOne,
  parTwo,
  parThree, // Trailing comma is now valid here.
) {}

// Before adding new parameter:
function myFunc(
  parOne,
  parTwo,
  parThree,
  parFour, // First and only change: new parameter.
) {}
```
