<<<<<<< HEAD
### 1. What is typeof operator?
 - [x] Answer: JavaScript provides a typeof operator that can examine a value and tell you what type it is:
```js
var a;
typeof a;				// "undefined"

a = "hello world";
typeof a;				// "string"

a = 42;
typeof a;				// "number"

a = true;
typeof a;				// "boolean"

a = null;
typeof a;				// "object" -- weird, bug

a = undefined;
typeof a;				// "undefined"

a = { b: "c" };
typeof a;				// "object"

```
### 2. What is the object type? 
 - [x] Answer: 
The `object` type refers to a compound value where you can set properties (named locations) that each hold their own values of any type.

```js
var obj = {
	a: "hello world", // property
	b: 42,
	c: true
};

obj.a;		// "hello world", accessed with doted notation
obj.b;		// 42
obj.c;		// true

obj["a"];	// "hello world", accessed with bracket notation
obj["b"];	// 42
obj["c"];	// true
```
Bracket notation is also useful if you want to access a property/key but the name is stored in another variable, such as:

```js
var obj = {
	a: "hello world",
	b: 42
};

var b = "a";

obj[b];			// "hello world"
obj["b"];		// 42
```
### 3. What is NaN property
 - [x] Answer: The NaN property is a global property that represents "Not-a-Number" value. i.e, It indicates that a value is not a legal number. It is very rare to use NaN in a program but it can be used as return value for few cases
```js
Math.sqrt(-1);
parseInt("Hello");
```

### 4. What will be the output when the following code is executed? Explain!
```js
     console.log(false == '0')
     console.log(false === '0')
```
 - [x] Answer: 
 - true
 - false
Explanation: == equal to, === equal to with datatype check!

### 5.  What will be the output of the following code?
```js
var foo = true;
        console.log(!foo);
        console.log(foo + 0);
        console.log(foo + "xyz");
        console.log(foo + false);
        console.log(foo && foo);
```
- [x] Answer:  Here you‘re looking for knowledge of how variable typing and the logical operators work in JavaScript. It will output the following to the console:
```js
        true
        1
        truexyz
        1
        true
```
### 6. Why is namespacing important when coding in JavaScript? Give an example of how you would implement namespacing to group this sample configuration data?

```js
          var DEBUG = true;
          var MAX_SIZE = 100;
          var FEED_URL = "http://myfeed.com/feed/";
          var POST_IDS = [1, 2, 3];
```
- [x] Answer:  Namespacing is used to group things like variables, functions and objects together with unique names. It helps to avoid naming conflicts, logically separate code and make code more reusable.

Namespacing in JavaScript is often done using objects. For the example above:
```js
 var Config = {
                 DEBUG: true,
                 MAX_SIZE: 100,
                 FEED_URL: "http://myfeed.com/feed/",
                 POST_IDS: [123, 456, 789]
          };

```


  A variable in this namespace can be accessed like so:

 ```js
     Config.MAX_SIZE;
  ```

### 7. What is the output out of the following code? Explain your answer.
```js
var a={},
    b={key:'b'},
    c={key:'c'};

a[b]=123;
a[c]=456;

console.log(a[b]);
```
- [x] Answer: The output of this code will be 456 (not 123).

The reason for this is as follows: When setting an object property, JavaScript will implicitly stringify the parameter value. In this case, since b and c are both objects, they will both be converted to "[object Object]". As a result, a[b] anda[c] are both equivalent to a["[object Object]"] and can be used interchangeably. Therefore, setting or referencing a[c] is precisely the same as setting or referencing a[b].

### 8. 
=======
### 1. What is NaN property
The NaN property is a global property that represents "Not-a-Number" value. i.e, It indicates that a value is not a legal number. It is very rare to use NaN in a program but it can be used as return value for few cases
```js
Math.sqrt(-1);
parseInt("Hello");
````

### 2. What is the reason to choose the name let as a keyword

`let` is a mathematical statement that was adopted by early programming languages like Scheme and Basic. It has been borrowed from dozens of other languages that use let already as a traditional keyword as close to var as possible.
>>>>>>> 33f1d2c... [feat:] general questions added
