# ES2021

## Numeric separators

```js
1_000_000_000      // A billion
101_475_938.38     // Hundreds of millions
0.000_001          // 1 millionth
1e10_000           // 10^10000 -- granted, far less useful / in-range...

const binary_literals = 0b1010_0001_1000_0101;
const hex_literals = 0xA0_B0_C0;
const bigInt_literals = 1_000_000_000_000n;
const octal_literal = 0o1234_5670;
```

## String.prototype.replaceAll

Currently there is no way to replace all instances of a substring in a string without the use of a global regexp (/regexp/g).

```js
const fruits = '🍎+🍐+🍓+';
const fruitsWithBanana = fruits.replace(/\+/g, '🍌');
console.log(fruitsWithBanana); //🍎🍌🍐🍌🍓🍌
```

A new `replaceAll` method has been added to the String prototype.

```js
const fruits = '🍎+🍐+🍓+';
const fruitsWithBanana = fruits.replaceAll('+', '🍌');
console.log(fruitsWithBanana); //🍎🍌🍐🍌🍓🍌
```

## Class private methods & private accessors

We can restrict the method being called outside of the class by generating private methods.

```js
class Person{

 #showTypeMethod(){
    console.log("This is a type");
 }

 showHelloMethod(){
    console.log("Hello World");
 }
}

const person = new Person();
person.showHelloMethod(); // Hello World
person.showTypeMethod(); // Error: person.showTypeMethod is not a function
```
