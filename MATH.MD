### 1. How do you generate random integers
You can use Math.random() with Math.floor() to return random integers. For example, if you want generate random integers between 1 to 10, the multiplication factor should be 10,
```js
Math.floor(Math.random() * 10) + 1; // returns a random integer from 1 to 10
Math.floor(Math.random() * 100) + 1; // returns a random integer from 1 to 100
```
Note: Math.random() returns a random number between 0 (inclusive), and 1 (exclusive)


### 2. What is the output of below code
```js
console.log(Math.max());
1: undefined
2: Infinity
3: 0
4: -Infinity
```
Answer
`-Infinity` is the initial comparant because almost every other value is bigger. So when no arguments are provided, `-Infinity` is going to be returned. Note: Zero number of arguments is a valid case.