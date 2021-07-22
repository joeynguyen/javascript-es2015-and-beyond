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
