### Questions about `for` operator in JavaScript

### 1.What language constructions do you use for iterating over object properties and array items?  

- [x] Answer:

For objects:
- `for` loops - `for (var property in obj) { console.log(property); }`. However, this will also iterate through its inherited properties, and you will add an obj.hasOwnProperty(property) check before using it.
- `Object.keys()` - `Object.keys(obj).forEach(function (property) { ... })`. `Object.keys()` is a static method that will lists all enumerable properties of the object that you pass it.
- `Object.getOwnPropertyNames()` - `Object.getOwnPropertyNames(obj).forEach(function (property) { ... })`.` Object.getOwnPropertyNames()` is a static method that will lists all enumerable and non-enumerable properties of the object that you pass it.
For arrays:
- `for` loops - `for (var i = 0; i < arr.length; i++)`. The common pitfall here is that var is in the function scope and not the block scope and most of the time you would want block scoped iterator variable. ES2015 introduces let which has block scope and it is recommended to use that instead. So this becomes: `for (let i = 0; i < arr.length; i++)`.
- `forEach` - `arr.forEach(function (el, index) { ... })`. This construct can be more convenient at times because you do not have to use the index if all you need is the array elements. There are also the `every` and `some` methods which will allow you to terminate the iteration early.

Most of the time, I would prefer the `.forEach` method, but it really depends on what you are trying to do. `for` loops allow more flexibility, such as prematurely terminate the loop using `break` or incrementing the iterator more than once per loop.

### 2. Write a loop that prints every number divisible by 3 from 1-200:
- [x] Answer:
```js
for (let i = 1; i < 201; i++) {
  if (i % 3 === 0) {
    console.log(i)
  }
}
```

### 3.  How do break and continue statements differ and where would you use each?
- [x] Answer:
  
`Break` statements cause the code to exit a loop immediately.
```js
for (let i = 0; i < 100; i++) {
  if (i === 10) { break; } // this ends the loop early (at 10 instead of 100)
  console.log('the current number is: ' + i)
}
```
`Continue` statements immediately jump to the next iteration of the loop.
```js
for (let i = 0; i < 100; i++) {
  if (i%2 === 0) { continue; } // skips even numbers
  console.log('The number is odd');
}
```



