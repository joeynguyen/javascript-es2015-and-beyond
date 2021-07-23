# New features I don't like

## ES2015

### Shorthand/"Enhanced" Object Literals

```js
// before
function createObject(name, data) {
    return {
        name: name,
        data: data,
        sum: function(a, b) { return a + b; }
    };
}

// after
function createObject(name, data) {
    return {
        name,
        data,
        sum(a, b) { return a + b; },
    };
}
```

Why I don't like it:

- refactoring can lead to issues because devs intending to change a variable name might accidentally change the object's property name
- confusing for new JS devs
  - doesn't look like an object
  - syntax too similar to object destructuring
- mixed use can be jarring to read

```js
function createObject(name, myData) {
  return { name, data: myData };
}
```

## ES2021

### Logical Assignment Operator

The logical assignment operator combines the logical operations(&&, || or ??) with assignment.

#### with `&&`

```js
var y = 2;
x &&= y;
console.log(x); // 2

// can be replaced with
x && (x = y);

// or
if (x) {
  x = y;
}
```

#### with `||`

```js
var x = 1;
var y = 2;
x ||= y;
console.log(x); // 1

// can be replaced with
x || (x = y);

// or
x = x || y;
```

#### with `??`

```js
// as a reminder `??` is Nullish Coalescing operator. It checks if a value is null or undefined.
var a;
var b = a ?? 5;
console.log(b); // 5

// Logical Assignment Operator with `??`
var x;
var y = 2;
x ??= y;
console.log(x); // 2

// equivalent to
x = x ?? (x = y);
```
