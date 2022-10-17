# Multiple Pointers Pattern

Creating **pointers** or values that correspond to an index or position and move towards the beginning, end or middle based on a certain condition.

**Very** effeient for solving problems with minimal space complexity as well

## Example

Write a function called sumZero wich accepts a sorted array of integers. The function should find the first pair where the sum is 0. Return array that includes both values or undefined if a pair does not exist.

```javascript
sumZero([-3, -2, -1, 0, 1, 2, 3]); //[-3,3]
sumZero([-2, 0, 1, 3]); // undefined
sumZero([1, 2, 3]); // undefined
```

### Naive Solution

- Time Complexity **O(n<sup>2</sup>)**
- Space Complexity **O(1)**

```javascript
function sumZero(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[i] + arr[j] === 0) {
        return [arr[i], arr[j]];
      }
    }
  }
}

sumZero([-4, -3, -2, -1, 0, 1, 2, 5]);
```

### Better Solution

- Time Complexity **O(n)**
- Space Complexity **O(1)**

Works from the ends in to find zero. Note this only works if the numbers are in sequential order.

```javascript
function sumZero(arr) {
  let left = 0;
  let right = arr.length - 1;
  while (left < right) {
    let sum = arr[left] + arr[right];
    if (sum === 0) {
      return [arr[left], arr[right]];
    } else if (sum > 0) {
      right--;
    } else {
      left++;
    }
  }
}
```
