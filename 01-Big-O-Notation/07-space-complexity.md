# Space Complexity

We can also use big O notation to analyze **space complexity:** how much hadditional memory do we need to allocate in order to run the code in our algorithm?

## What about the inputs?

**Auxiliary space complexity** refers to space required by the algorithm, not including space taken up by the inputs.

## Space Complexity in JS

- Most primitives (booleans, numbers, undefine, null) are constant space
- Strings require **O(n)** space, where n is the string length
- Reference types are generally O(n), where n is the length (for arrays) or the number of keys (for objects)

## An Example

In the example below we have **O(1) space** because we have 2 variables, total and i. The values may change but the amount of memory needed does not.

```javascript
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```

In the example below we have **O(n) space** because the lenght of the **newArr** is dependent on the length of the array passed to the function.

```javascript
function double(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    newArr.push(2 * arr[i]);
  }
  return newArr;
}
```
