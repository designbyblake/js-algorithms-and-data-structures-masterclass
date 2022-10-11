# Counting Operations

The number of operations in functions directly impacts the function speed.

```javascript
function addUpTo(n) {
  return (n * (n + 1)) / 2;
}
```

This function has a total of 3 operations regardless of the value of n. They are 1 multiplication, 1 addition, and 1 division.

```javascript
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```

This function only multiple operations. There is a single assignment for the initial total and single assignment in the loop.

There is also 1 comparision, 1 addition and 1 assignments in the loop, however these run n times. In addition there is a 1 addition and 1 assignment inside the loop. This is 5 operations that run n times. If n === 1,000,000 we have 5,000,000 operations.

**5n + 2**
