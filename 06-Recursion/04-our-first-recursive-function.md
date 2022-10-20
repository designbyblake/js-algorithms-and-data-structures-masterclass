# Our First Recursie Function

## How recursive functions work

Invoke the **same** function with a different input until you reach your **base case** (where the function stops being called).

## Base Case

The condition when the recursion ends. **This is the most important concept to understand**

## Two parts of a recursive function

- Base Case
- Different Input

## Example

```javascript
// Recursive Version
function countDown(num) {
  if (num <= 0) {
    console.log("All done!");
    return;
  }
  console.log(num);
  num--;
  countDown(num);
}
countDown(3);

// Iterative Version
function countDown(num) {
  for (var i = num; i > 0; i--) {
    console.log(i);
  }
  console.log("All done!");
}
```
