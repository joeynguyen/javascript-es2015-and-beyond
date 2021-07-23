# ES2018

## Object spread operator

```js
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = {
  ...obj1,
  c: 30
};

console.log(obj2);    // → {a: 10, b: 20, c: 30}

// it can also be used to overwrite existing properties

const obj3 = {
  ...obj2,
  a: 4
};
console.log(obj3);    // → {a: 4, b: 20, c: 30}
```

a simpler syntax than `Object.assign()` which achieves the same purpose

```js
const obj1 = {
  a: 10,
  b: 20
};

const obj2 = Object.assign(obj1, {c: 30});
console.log(obj2);    // → {a: 10, b: 20, c: 30}
```

Nice way to copy an object variable to a new variable.

```js
const obj1 = {a: 10, b: 20, c: 30};
// JS creates a reference if you do this:
const justARef = obj1;
console.log(justARef === obj1);    // → true

justARef.d = 40;
console.log(justARef);    // → {a: 10, b: 20, c: 30, d: 40}
console.log(obj1);    // → {a: 10, b: 20, c: 30, d: 40}

// make a copy of arr1 and assign to a new constiable
const obj2 = {a: 1, b: 2, c: 3};
const copy = {...obj2};

console.log(copy === obj2);    // → false
copy.d = 5;
console.log(obj2);    // → {a: 1, b: 2, c: 3}
console.log(copy);    // → {a: 1, b: 2, c: 3, d: 5}
```

## Object rest parameter

Rest element must be last element (doesn't have to be named `rest`).

```js
const obj = {
  a: 10,
  b: 20,
  c: 30
};

const {a, ...rest} = obj;

console.log(a);       // → 10
console.log(rest);    // → {b: 20, c: 30}
```
