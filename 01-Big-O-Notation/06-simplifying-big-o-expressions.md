# Simplifying Big O Expressions

## Constants Don't Matter

- O(2n) simplified to **O(n)**, as n increases run time increases at the same rate
- O(500) simplified to **O(1)**, constant run time
- 0(13n<sup>2</sup>) simplified to **O(n<sup>2</sup>)**

## Smaller Terms Don't Matter

- O(n + 10) simplified to **O(n)**
- 0(1000n + 50) simplified to **O(n)**
- O(n<sup>2</sup> + 5n + 8) simplified to**O(n<sup>2</sup>)**

## Big O Shorthands

1. Arithmetic operations are constant
1. Variable assignment is constant
1. Accessing elements in an array(by index) or object (by key) is constant run time
1. In a loop, the complexity is the length of the loop times the compleity of whatever happens inside of the loop
