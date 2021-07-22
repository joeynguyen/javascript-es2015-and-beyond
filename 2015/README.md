# ES2015

1. Default Parameters
2. Template Literals
3. Multi-line Strings
4. Destructuring Assignment
5. Enhanced Object Literals
6. Arrow Functions
7. Promises
8. Block-Scoped Constructs Let and Const
9. Classes
10. Modules
11. Array spread operator
12. Array rest operator

### Array spread operator

```js
const arr1 = [10, 20, 30];

// make a copy of arr1
const copy = [...arr1];

console.log(copy);    // → [10, 20, 30]

const arr2 = [40, 50];

// merge arr2 with arr1
const merge = [...arr1, ...arr2];

console.log(merge);    // → [10, 20, 30, 40, 50]
```

also comes in handy in situations where an array must be passed in as separate arguments to a function

```js
const arr = [10, 20, 30]

// equivalent to
// console.log(Math.max(10, 20, 30));
console.log(Math.max(...arr));    // → 30
```

### Array rest parameter

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
