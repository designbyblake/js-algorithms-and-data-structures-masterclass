# Official Intro to Big O

> Big O Notation is a way to formalize fuzzy counting.

> It allows us to talk formally about how the runtime of an algorithm grows as the inputs grow

> We say than an algorithm is **O(f(n))** if the number of simple operations the computer has to do is eventually less than a constant times **f(n)**, as **n** increases

- f(n) could be linear (f(n) = n) - The loop example from previous lessons
- f(n) could be quadratic (f(n) = n<sup>2</sup>)
- f(n) could be constant (f(n) = 1) - The 1 line example
- f(n) could be something entirely diffrent!

Big O is the worst case scenario.

## O(n)

The example below is O of n times 2 for 2 loops but it is simplified to O of n. Increasing n creates a straight diagonal line on the tracking chart.

```javascript
function countUpAndDown(n) {
  console.log("Going up!");
  for (var i = 0; i < n; i++) {
    console.log(i);
  }
  console.log("At the top!\nGoing down...");
  for (var j = n - 1; j >= 0; j--) {
    console.log(j);
  }
  console.log("Back down. Bye!");
}
```

## O(n \* n)

In this example there is a loop in a loop, n<sup>2</sup>.

- printAllPairs(2); // 4 Console Logs
- printAllPairs(4); // 16 Console Logs
- printAllParis(8); // 64 Console Logs

```javascript
function printAllPairs(n) {
  for (var i = 0; i < n; i++) {
    for (var j = 0; j < n; j++) {
      console.log(i, j);
    }
  }
}
```
