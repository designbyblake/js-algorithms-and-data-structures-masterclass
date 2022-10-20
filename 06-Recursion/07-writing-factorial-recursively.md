# Writing Factorial Recursively

4! Factorial, Four Factorial = 4 _ 3 _ 2 \* 1

```javascript
function factorial(num) {
  if (num === 1) return 1;
  return num * factorial(num - 1);
}
```
