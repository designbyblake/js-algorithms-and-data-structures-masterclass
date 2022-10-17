# Frequency Counter Pattern

This pattern uses objcts or sets to collect values/frequencies of values.

This can often avoid the need for nested loops of **(On<sup>2</sup>)** operations with arrays and string.

## Example

Write a function called **same** which accepts two arrays. The function should return true if every value in the array has it's corresponding value squared in teh second array. The frequency of values must be the same.

```javascript
same([1, 2, 3], [4, 1, 9]); // true - order does not matter
same([1, 2, 3], [1, 9]); // false
same([1, 2, 1], [4, 4, 1]); // false (must be same frequency)
```

### Not great

```javascript
// ** is Exponentiation
// 2 ** 2 = 4
// 2 ** 3 = 8
function same(arr1, arr2) {
  if (arr1.length !== arr2.length) {
    return false;
  }
  for (let i = 0; i < arr1.length; i++) {
    let correctIndex = arr2.indexOf(arr1[i] ** 2);
    if (correctIndex === -1) {
      return false;
    }
    console.log(arr2);
    arr2.splice(correctIndex, 1);
  }
  return true;
}
```

### Refactored

```javascript
function same(arr1, arr2) {
  if (arr1.length !== arr2.length) {
    return false;
  }
  let frequencyCounter1 = {};
  let frequencyCounter2 = {};
  for (let val of arr1) {
    frequencyCounter1[val] = (frequencyCounter1[val] || 0) + 1;
  }
  for (let val of arr2) {
    frequencyCounter2[val] = (frequencyCounter2[val] || 0) + 1;
  }
  console.log(frequencyCounter1);
  console.log(frequencyCounter2);
  for (let key in frequencyCounter1) {
    if (!(key ** 2 in frequencyCounter2)) {
      return false;
    }
    if (frequencyCounter2[key ** 2] !== frequencyCounter1[key]) {
      return false;
    }
  }
  return true;
}

same([1, 2, 3, 2, 5], [9, 1, 4, 4, 11]);
```

## Anagram

```javascript
// My solution
function validAnagram(str1, str2) {
  // if not the same length return false
  if (str1.length !== str2.length) return false;

  // create objects to store the character count as keys
  const word1 = {};
  const word2 = {};

  // loop through strings and add count to keys
  for (let val of str1) {
    word1[val] = (word1[val] || 0) + 1;
  }

  for (let val of str2) {
    word2[val] = (word2[val] || 0) + 1;
  }
  // loop through object1 and make sure lengths of keys match object 2
  for (let key in word1) {
    if (word1[key] !== word2[key]) return false;
  }

  return true;
}

// Colt's solution, uses 2 loops instead of 3
function validAnagram(first, second) {
  if (first.length !== second.length) {
    return false;
  }

  const lookup = {};

  for (let i = 0; i < first.length; i++) {
    let letter = first[i];
    // if letter exists, increment, otherwise set to 1
    lookup[letter] ? (lookup[letter] += 1) : (lookup[letter] = 1);
  }
  console.log(lookup);

  for (let i = 0; i < second.length; i++) {
    let letter = second[i];
    // can't find letter or letter is zero then it's not an anagram
    if (!lookup[letter]) {
      return false;
    } else {
      lookup[letter] -= 1;
    }
  }

  return true;
}
```
