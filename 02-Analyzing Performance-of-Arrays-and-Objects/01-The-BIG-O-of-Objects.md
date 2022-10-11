# The Big O of Objects

## Objects

Unordered, key value pairs!

```javascript
let student = {
  githubUserName: "designbyblake",
  isLearningNewSkills: true,
  dogs: ["Ein", "Chewie"],
};
```

- Good for when you don't need order
- When you need fast access/ and removal

### Big O of Objects

- Insertion - **O(1)**
- Removal - **O(1)**
- Searching - **O(n)**
- Access - **O(1)**

### Big O of Object Methods

Object.keys - **O(n)**

```javascript
Object.keys(student);
["githubUserName", "isLearningNewSkills", "dogs"];
```

Object.values - **O(n)**

```javascript
Object.values(student);
["designbyblake", true, ["Ein", "Chewie"]];
```

Object.entries - **O(n)**

```javascript
Object.entries(student);
[
  ["githubUserName", "designbyblake"],
  ["isLearningNewSkills", true],
  ["dogs", ["Ein", "Chewie"]],
];
```

hasOwnProperty - **O(1)**

```javascript
student.hasOwnProperty("githubUserName"); // true
student.hasOwnProperty("cats"); // false
```
