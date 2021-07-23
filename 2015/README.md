# ES2015

1. Block-Scoped Constructs `let` and `const`
2. Destructuring Assignment
3. Template Literals/Strings
4. Computed Property Names
5. Default Parameters
6. Arrow Functions
7. Promises
8. Classes
9. Modules
10. Array spread operator
11. Array rest operator

## Block-Scoped Constructs `let` and `const`

```js
// before
var isTrue = true;

if (isTrue) {
    var notBlockScoped = true;
}
console.log('notBlockScoped', notBlockScoped); // true

// after
if (isTrue) {
    let blockScoped = true;
}
console.log('blockScoped', blockScoped);
// Uncaught ReferenceError: blockScoped is not defined
```

Difference between `const` and `let`

```js
// `let` can be reassigned to a different value
let a = 'a'
a = 'not a';
console.log('a', a); // "not a"

// `const` cannot be reassigned to a different reference or primative value
const b = 'b';
b = 'still b';
// Uncaught TypeError: Assignment to constant variable.

// however, despite the connotation of its name, `const` CAN be mutated because it's still the same reference
const c = {
    color: 'red',
};
c.number = 3;
console.log('c', c); // { color: 'red', number: 3}
```

## Destructuring Assignment

makes it possible to unpack values from arrays, or properties from objects, into distinct variables

```js
const [a, b] = [30, 60];
console.log(a); // 30
console.log(b); // 60

const myName = {
    first: "Terry",
    last: "Cruz"
}
const { first, last } = myName;
console.log(first); // "Terry"
console.log(last); // "Cruz"
```

## Template Literals/Strings

allows for string interpolation

```js
// before
var name = "Joey";
console.log('Yo, ' + name + '!'); // → "Yo, Joey!"

// after
var name = "Joey";
console.log(`Yo, ${name}!`); // → "Yo, Joey!"
```

can also be used for multi-line strings

```js
// before
var myString = 'string text line 1\n' +
'string text line 2\n' +
'string text line 3'

// after
var myString = `string text line 1
string text line 2
string text line 3`
```

## Computed Property Names

```js
var propName = 'name'
var myObj = {
    [propName]: "John"
}; // → {name: "John"}
```

## Default Function Parameters

allow named parameters to be initialized with default values if no value or undefined is passed

```js
function multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5, 2)); // 10

console.log(multiply(5)); // 5
```

## Arrow Functions

```js
// before
function sum(a, b) { return a + b; }

// after
var sum = (a, b) => a + b; // implicit `return` if not wrapped in curly brackets
```

another example

```js
// before
button.addEventListener('click', function(event) {
  console.log('The button has received a click', event);
});

// after
button.addEventListener('click', (event) => {
  console.log('The button has received a click', event);
});
```

## Promises

A Promise is always in one of these states:

- *pending*: initial state, neither fulfilled nor rejected.
- *fulfilled*: meaning that the operation was completed successfully.
- *rejected*: meaning that the operation failed.

The `Promise` object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

- most commonly used for fetching data
- the `fetch()` function returns a `Promise`

```js
// fulfilled
fetch('https://jsonplaceholder.typicode.com/todos')
  .then(response => response.json())
  .then(data => console.log(JSON.stringify(data)))

// rejected
fetch('https://jsonplaceholder.typicode.com/aslfdjk')
  .then(response => response.json())
  .then(data => console.log(JSON.stringify(data)))
  .catch(err => console.log('are you sure you have the right URL?'))
```

## Classes

```js
class Person{
 showHelloMethod(){
    console.log("Hello World");
 }
}

const person = new Person();
person.showHelloMethod(); // Hello World
```

## Modules

```js
// exampleFunction.js
export function exampleFunction() {
  console.log("I'm an example.");
}

// randomFile.js
import { exampleFunction } from './example-function';

exampleFunction();
```

## Array spread operator

```js
const arr1 = [10, 20, 30];
const arr2 = [40, 50];

const merge = [...arr1, ...arr2];
console.log(merge); // → [10, 20, 30, 40, 50]
```

Nice way to copy an array variable to a new variable.

```js
var arr1 = [10, 20, 30];
// JS creates a reference if you do this:
var justARef = arr1;
console.log(justARef === arr1);    // → true

justARef.push(40);
console.log(justARef);    // → [10, 20, 30, 40]
console.log(arr1);    // → [10, 20, 30, 40]

// make a copy of arr1 and assign to a new variable
var arr2 = [1, 2, 3];
var copy = [...arr2];

console.log(copy === arr2);    // → false
copy.push(5);
console.log(arr2);    // → [1, 2, 3]
console.log(copy);    // → [1, 2, 3, 5]
```

also comes in handy in situations where an array must be passed in as separate arguments to a function

```js
const arr = [10, 20, 30]

console.log(Math.max(10, 20, 30));
// equivalent to
console.log(Math.max(...arr));    // → 30
```

## Array rest parameter

Rest element must be last element (doesn't have to be named `rest`).

```js
const arr = [10, 20, 30];
const [x, ...rest] = arr;

console.log(x);       // → 10
console.log(rest);    // → [20, 30]
```

## new `String` methods: 

- `startsWith`: checks if the string starts with the characters of another string. Returns boolean
- `endsWith`: checks if the string ends with the characters of another string. Returns boolean
- `repeat`: takes an integer *n* as argument and returns the string *n* times.

```js
console.log("Never gonna give you up");
console.log("Never gonna give...\n".repeat(2));
console.log("Give you up!");
```
