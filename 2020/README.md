# ES2020

## Nullish Coalescing Operator

Use case when writing React:

without:

```jsx
const { score } = props;
// score could be `0` so we can't do {score || '?'}
<h5>Score: {score !== null && score !== undefined ? score : '?'}</h5>
```

with:

```jsx
const { score } = props;
<h5>Score: {score ?? '?'}</h5>
```

## Optional Chaining

assuming a fetched response object with the following value:

```js
const response = {
  type : "customer",
  details : {
    age : 22,
    name : {
      first: "Homer",
      middle: "J",
      last: "Simpson",
    }
  }
};
```

without:

```js
const firstName = response && response.details && response.details.name && response.details.name.first
```

with:

```js
const data = response?.details?.name?.first
```

Replaces the need for something like `lodash.get` which can do the following:

```js
const data = _.get(response, ['details', 'name', 'first']);
```

## globalThis

The root global object is different depending on which environment you're working in:

- `window` for browsers,
- `global` for Node,
- `self` for web workers

`globalThis` always refers to the global object, no matter where you are executing your code

```js
// in browser
globalThis.setTimeout === window.setTimeout // true
```

## BigInt

new primitive type

```js
BigInt("1") // 1n
BigInt("1") === 1n // true

console.log(typeof 1n);
//  bigint

let oldNumMax = Number.MAX_SAFE_INTEGER;
console.log(oldNumMax);
//  9007199254740991

console.log(++oldNumMax);
//  9007199254740992

console.log(++oldNumMax);
//  9007199254740992

let bigIntNum = 9007199254740991n;

console.log(bigIntNum)
//  9007199254740991n

console.log(++bigIntNum);
//  9007199254740992n

console.log(++bigIntNum);
//  9007199254740993n

console.log(bigIntNum + bigIntNum);
//  18014398509481986n
```
