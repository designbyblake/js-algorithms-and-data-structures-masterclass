# Writing Factorial Iteratively

4! Factorial, Four Factorial = 4 _ 3 _ 2 \* 1

```javascript
function factorial(num) {
  let total = 1;
  for (let i = num; i > 1; i--) {
    total *= i;
  }
  return total;
}
```
