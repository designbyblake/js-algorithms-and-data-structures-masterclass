# The Call Stack

- It's a **stack** data structure
- Anytime a function is involded it is place (**pushed**) on top of the call stack
- When JavaScript sees the **return** keyword or when the function ends, the compiler will remove **(pop)**

Added to the top and removed frm the top

## Callstack Example

```javascript
function takeShower() {
  return "Showering!";
}

function eatBreakfast() {
  let meal = cookFood();
  return `Eating ${meal}`;
}

function cookFood() {
  let items = ["Oatmeal", "Eggs", "Protein Shake"];
  return items[Math.floor(Math.random() * items.length)];
}
function wakeUp() {
  takeShower();
  eatBreakfast();
  console.log("Ok ready to go to work!");
}

wakeUp();
```

### Stack 1

- wakeup();

### Stack 2

- takeShower();
- wakeup();

### Stack 3

- eatBreakfast();
- wakeup();

### Stack 4

- cookFood();
- eatBreakfast();
- wakeup();

### Stack 5

- eatBreakfast();
- wakeup();

### Stack 6

- wakeup();

### Stack 7

Done
