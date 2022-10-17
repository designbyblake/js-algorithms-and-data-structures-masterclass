# Sliding Window Pattern

This pattern involes creating a **window** which can either be an array or number from one position to another.

Depending on a certain condition, the window either increases or closes (and a new window is created).

## Example

### Naive

The example below has a nested loop making this **O(n<sup>2</sup>)**. It adds all numbers on every loop.

```javascript
function maxSubarraySum(arr, num) {
  if (num > arr.length) {
    return null;
  }
  var max = -Infinity;
  for (let i = 0; i < arr.length - num + 1; i++) {
    temp = 0;
    for (let j = 0; j < num; j++) {
      temp += arr[i + j];
    }
    if (temp > max) {
      max = temp;
    }
  }
  return max;
}

maxSubarraySum([2, 6, 9, 2, 1, 8, 5, 6, 3], 3);
```

### Refactored

This refactored has two loops but they are not nested. **O(n)**

```javascript
function maxSubarraySum(arr, num) {
  let maxSum = 0;
  let tempSum = 0;

  // If the array length is less than the numbers needed to add together it gets short circuited .

  if (arr.length < num) return null;
  // get the initial tempSum
  for (let i = 0; i < num; i++) {
    tempSum += arr[i];
  }
  // Single loop that slides the window up
  for (let i = num; i < arr.length; i++) {
    // Instead of adding all the numbers back up we subtract the number to the left of the group and than add the next number

    // tempSum = 17; // (2+6+9)
    // tempSump = 17 - 2 + 2; // 17 first loop
    // tempSum = 17 - 6 + 1 //  12 second loop
    // tempSum = 12 - 9 + 8 // 11 third loop
    tempSum = tempSum - arr[i - num] + arr[i];
    maxSum = Math.max(maxSum, tempSum);
  }
  return maxSum;
}

maxSubarraySum([2, 6, 9, 2, 1, 8, 5, 6, 3], 3);
```
