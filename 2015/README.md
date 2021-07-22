# ES2015

1. Block-Scoped Constructs Let and Const
2. Destructuring Assignment
3. Template Literals
4. Default Parameters
5. Multi-line Strings
6. Arrow Functions
7. Promises
8. Classes
9. Modules
10. Array spread operator
11. Array rest operator
12. Computed Property Names

## Block-Scoped Constructs Let and Const

```js
// before
var isTrue = true;

if (isTrue) {
    var notBlockScoped = true;
}
console.log(notBlockScoped); // true

// after
if (isTrue) {
    let blockScoped = true;
}
console.log(blockScoped);
// Uncaught ReferenceError: blockScoped is not defined
```

Difference between `const` and `let`

```js
// `let` can be reassigned to a different data type
let a = 'a'
a = 1;
console.log(a); // 1

// `const` cannot be reassigned to a different data type
const b = 'b';
b = 2;
// Uncaught SyntaxError: Identifier 'b' has already been declared

// however, despite the connotation of its name, `const` CAN be mutated
const c = {
    color: 'red',
};
c.number = 3;
console.log(c); // { color: 'red', number: 3}
```

## Destructuring Assignment

```js
let [a, b] = [30, 60];
console.log(a); // 30
console.log(b); // 60

let myName = {
    first: "Terry",
    last: "Cruz"
}
let { first } = myName;
console.log(first); // "Terry"
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

## Computed Property Names

```js
var propName = 'name'
var myObj = {
    [propName]: "John"
}; // → {name: "John"}
```

## Template Literals

```js
var name = "Joey";
console.log(`Yo, ${name}!`); // → "Yo, Joey!"
```

## Modules

```js
// exampleFunction.js
export function exampleFunction() {
  console.log("I'm an example. #TrueStory");
}

// randomFile.js
import { exampleFunction } from './example-function';

exampleFunction();
```

## Array spread operator

```js
const arr1 = [10, 20, 30];
const arr2 = [40, 50];

const merge = [...arr1, ...arr2]; // → [10, 20, 30, 40, 50]
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

// equivalent to
// console.log(Math.max(10, 20, 30));
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

13. String methods: 

- startsWith: checks if the string starts with the characters of another string. Returns boolean
- endsWith: checks if the string ends with the characters of another string. Returns boolean
- repeat: takes an integer *n* as argument and returns the string *n* times.
