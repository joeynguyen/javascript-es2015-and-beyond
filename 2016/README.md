# ES2016

## Array.prototype.includes

takes 2 parameters: 1st is the item you want to find, 2nd is the `fromIndex`

```js
const fruits = [🍐, 🥑, 🍇]
fruits.includes(🥑)      // true
fruits.includes(🍉)      // false
fruits.includes(🍇, 3)   // false
fruits.includes(🍇, -1)  // true
```

## Exponentiation Operator

The exponential operator `**` is an infix operator for exponentiation.

```js
5 ** 4 === Math.pow(5,4); // true
```
