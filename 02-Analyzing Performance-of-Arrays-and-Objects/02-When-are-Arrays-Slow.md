# When are Arrays Slow?

## When to use Arrays?

- When you need order.
- When you need fast access/ insertion and removal

## Big O of Arrays

- Insertion - It depends...
  - .push() - **O(1)** - added at end of array
  - .unshift() - **O(n)** - added at start of array, full array is reindexed
- Removal -It depends ...
  - .pop() - **O(1)** - removed at end of array
  - .shift()- **O(n)** - removed at start of array, full array is reindexed
- Searching - **O(n)**
- Access - **O(1)**
