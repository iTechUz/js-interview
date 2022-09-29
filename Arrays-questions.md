### 1.  How can you create an Array in JavaScript?
You can define arrays using the array literal as follows-
```js
var x = [];
var y = [1, 2, 3, 4, 5];
```

### 2. What are the .slice() and .splice() methods, and how do they differently affect arrays?

- [x] Answer:

`.slice()` doesn’t modify the original array, and returns the elements from the array, minus the instructed elements to be sliced off based on the numbers instructed in the brackets.

If one parameter is written, this will be used as the start parameter, and if two parameters are written, the second element will be used as the end parameter.

```js
const reasonsToTryBootdotdev = ["free trial", "interactive", "browser based", "helpful community", "range of content"]; 

reasonsToTryBootdotdev.slice(2,4)
// ["browser based", "helpful community"]
```
The `.splice()` method instead modifies the original array. It returns the deleted elements as arrays, and is often use to insert or remove elements to or from an existing array.

```js
const reasonsToTryBootdotdev = ["free trial", "interactive", "browser based", "helpful community", "range of content"]; 
const removed = reasonsToTryBootdotdev.splice(2,4)
console.log(reasonsToTryBootdotdev)
// ["free trial","interactive"]

console.log(removed)
// ["browser based","helpful community","range of content"]
```