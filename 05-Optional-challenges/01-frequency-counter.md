# Frequency Counter - sameFrequency

Write a function called sameFrequency. Given two positive integers, find out if the two numbers have the same frequency of digits.

Your solution MUST have the following complexities:

Time: O(N)

Sample Input:

1. sameFrequency(182,281) // true
1. sameFrequency(34,14) // false
1. sameFrequency(3589578, 5879385) // true
1. sameFrequency(22,222) // false

## My solution

```javascript
function sameFrequency(num1, num2) {
  const num1String = num1.toString();
  const num2String = num2.toString();

  if (num1String.length !== num2String.length) return false;

  const frequency1 = {};
  const frequency2 = {};

  for (let val of num1String) {
    frequency1[val] = (frequency1[val] || 0) + 1;
  }

  for (let val of num2String) {
    frequency2[val] = (frequency2[val] || 0) + 1;
  }

  for (let key in frequency1) {
    if (!frequency2.hasOwnProperty(key)) return false;
    if (frequency1[key] !== frequency2[key]) return false;
  }

  return true;
}
```
