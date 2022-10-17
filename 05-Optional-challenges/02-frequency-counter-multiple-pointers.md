# Frequency Counter / Multiple Pointers - areThereDuplicates

Implement a function called, areThereDuplicates which accepts a variable number of arguments, and checks whether there are any duplicates among the arguments passed in. You can solve this using the frequency counter pattern OR the multiple pointers pattern.

## Examples:

1. areThereDuplicates(1, 2, 3) // false
1. areThereDuplicates(1, 2, 2) // true
1. areThereDuplicates('a', 'b', 'c', 'a') // true

## Restrictions:

- Time - O(n)
- Space - O(n)

### Bonus:

- Time - O(n log n)
- Space - O(1)

## Solutions

### Mine

```javascript
function areThereDuplicates() {
  if (arguments.length === 0 || arguments === "undefined") return false;
  let compare = {};

  for (let key of arguments) {
    if (compare.hasOwnProperty(key)) return true;
    compare[key] = true;
  }
  return false;
}
```

### Second solution

Updated the loop because the Udemey platform was throwing a type error but original code worked everywhere else.

```javascript
function areThereDuplicates() {
  if (arguments.length === 0 || arguments === "undefined") return false;
  let compare = {};

  for (let i = 0; i < arguments.length; i++) {
    const key = arguments[i];
    if (compare.hasOwnProperty(key)) return true;
    compare[key] = true;
  }
  return false;
}
```

### Solution with multiple pointers

```javascript
function areThereDuplicates(...args) {
  // Two pointers
  args.sort((a, b) => a > b);
  let start = 0;
  let next = 1;
  while (next < args.length) {
    if (args[start] === args[next]) {
      return true;
    }
    start++;
    next++;
  }
  return false;
}
```

### Solution one liner

```javascript
function areThereDuplicates() {
  return new Set(arguments).size !== arguments.length;
}
```
