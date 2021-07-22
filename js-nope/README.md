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
