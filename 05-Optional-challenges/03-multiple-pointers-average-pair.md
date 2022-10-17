# Multiple Pointers - averagePair

Write a function called averagePair. Given a sorted array of integers and a target average, determine if there is a pair of values in the array where the average of the pair equals the target average. There may be more than one pair that matches the average target.

Bonus Constraints:

Time: O(N)

Space: O(1)

Sample Input:

1. averagePair([1,2,3],2.5) // true
1. averagePair([1,3,3,5,6,7,10,12,19],8) // true
1. averagePair([-1,0,3,4,5,6], 4.1) // false
1. averagePair([],4) // false

## My Solution

- I double the average to not have to divide every loop iteration by 2.
- I start at both ends of the array and add 2 numbers together.
  - If the sum === targetSum; return true, done.
  - If sum > targetSum, subtract right by 1 and loop again
  - If sum < targetSum, add left by 1 and loop again

```javascript
function averagePair(arr, average) {
  const targetSum = average * 2;
  let left = 0;
  let right = arr.length - 1;

  while (left < right) {
    let sum = arr[left] + arr[right];
    if (sum === targetSum) {
      return true;
    } else if (sum > targetSum) {
      right--;
    } else {
      left++;
    }
  }

  return false;
}
```
