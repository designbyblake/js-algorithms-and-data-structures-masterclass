# Helper Method Recursion

Essentially a function within a function that handles the recursion.

## Why do this?

In the example below we need to store information in an array. If we have the array inside the recursive function it will be reset on each call.

If we have it outside the function it is scoped in places we don't need it.

```javascript
function collectOddValues(arr) {
  let result = [];

  function helper(helperInput) {
    if (helperInput.length === 0) {
      return;
    }

    if (helperInput[0] % 2 !== 0) {
      result.push(helperInput[0]);
    }

    helper(helperInput.slice(1));
  }

  helper(arr);

  return result;
}

collectOddValues([1, 2, 3, 4, 5, 6, 7, 8, 9]);
```
