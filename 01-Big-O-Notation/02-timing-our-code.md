# Timing Our Code

Time the code using _performance.now()_. Store as variable before calling function and again after, subtract the after by before and divide by 1000 to convert to seconds.

The problem is that different machines as well as the same machines may record different times. For fast algorithms, speed measurements may not be precise enough.

```javascript
let t1 = performance.now();
functionName();
let t2 = performance.now();
console.log(`Time Elapsed: ${(t2 - t1) / 1000} seconds.`);
```

## Slower

```javascript
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}

let t1 = performance.now();
addUpTo(1_000_000_000);
let t2 = performance.now();
console.log(`Time Elapsed: ${(t2 - t1) / 1000} seconds.`);
```

## Faster

```javascript
function addUpTo(n) {
  return (n * (n + 1)) / 2;
}
let t1 = performance.now();
addUpTo(1_000_000_000);
let t2 = performance.now();
console.log(`Time Elapsed: ${(t2 - t1) / 1000} seconds.`);
```
