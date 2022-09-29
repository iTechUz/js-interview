### Questions about `functions`  in JavaScript

### 1.What are arrow functions and what benefits do they bring in your code?
- [x] Answer:
  
Arrow functions were introduced in ES6 and are a shorthand version of writing traditional functions. They save room and can make code more easily readable, are quicker to write, and can make coding more efficient. They also inherit the parent version of `this`.
```js
// pre-ES6 traditional way
function (height) {
  return height + 10;
}

// post-ES6 way with arrow functions
height => height + 10;
```
### 2.  What will the following code output? Why?

```js
 function foo(){
          function bar() {
            return ’a‘;
          }
          return bar();
          function bar() {
            return ’b‘;
          }
        }
```
- [x] Answer: Here you‘re testing detailed knowledge of a critical JavaScript concept called Hoisting.

Counterintuitively, the program will output b. This is because both of the bar() functions in the code snippet will be hoisted to the top of the scope. The second one returning the string ’b‘ will be hoisted after the first, so that function will be called in the return statement.


### 3. In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

```js
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```
- [x] Answer: The values will be logged in the following order:
```js
1
4
3
2
```

Let’s first explain the parts of this that are presumably more obvious:

1 and 4 are displayed first since they are logged by simple calls to console.log() without any delay

2 is displayed after 3 because 2 is being logged after a delay of 1000 msecs (i.e., 1 second) whereas 3 is being logged after a delay of 0 msecs.

OK, fine. But if 3 is being logged after a delay of 0 msecs, doesn’t that mean that it is being logged right away? And, if so, shouldn’t it be logged before 4, since 4 is being logged by a later line of code?

The answer has to do with properly understanding JavaScript events and timing.

The browser has an event loop which checks the event queue and processes pending events. For example, if an event happens in the background (e.g., a script onload event) while the browser is busy (e.g., processing an onclick), the event gets appended to the queue. When the onclick handler is complete, the queue is checked and the event is then handled (e.g., the onload script is executed).

Similarly, setTimeout() also puts execution of its referenced function into the event queue if the browser is busy.

When a value of zero is passed as the second argument to setTimeout(), it attempts to execute the specified function “as soon as possible”. Specifically, execution of the function is placed on the event queue to occur on the next timer tick. Note, though, that this is not immediate; the function is not executed until the next tick. That’s why in the above example, the call to console.log(4) occurs before the call to console.log(3) (since the call to console.log(3) is invoked via setTimeout, so it is slightly delayed).

### 4. What will the following code output to the console:
```js
console.log((function f(n){return ((n > 1) ? n * f(n-1) : n)})(10));
```
- [x] Answer:he code will output the value of 10 factorial (i.e., 10!, or 3,628,800).

Here’s why:

The named function f() calls itself recursively, until it gets down to calling f(1) which simply returns 1. Here, therefore, is what this does:
```js
f(1): returns n, which is 1
f(2): returns 2 * f(1), which is 2
f(3): returns 3 * f(2), which is 6
f(4): returns 4 * f(3), which is 24
f(5): returns 5 * f(4), which is 120
f(6): returns 6 * f(5), which is 720
f(7): returns 7 * f(6), which is 5040
f(8): returns 8 * f(7), which is 40320
f(9): returns 9 * f(8), which is 362880
f(10): returns 10 * f(9), which is 3628800
```
### 5 What will the following code output to the console and why:

```js
var hero = {
    _name: 'John Doe',
    getSecretIdentity: function (){
        return this._name;
    }
};

var stoleSecretIdentity = hero.getSecretIdentity;

console.log(stoleSecretIdentity());
console.log(hero.getSecretIdentity());
```
- [x] Answer: The code will output:
 ```js
 undefined
  John Doe
```
The first `console.log` prints undefined because we are extracting the method from the hero object, so stoleSecretIdentity() is being invoked in the global context (i.e., the window object) where the _name property does not exist.

One way to fix the stoleSecretIdentity() function is as follows:

### 6. What is the isNaN function?
- [x] Answer: 

The `isNaN` function determines whether a value is, or is not, a number (Not-a-Number). If the value is not a number, it will evaluate to `true`, and if the value is a number, it will evaluate to `false`.


### 7. What will the code below output to the console and why?
```js
var myObject = {
    foo: "bar",
    func: function() {
        var self = this;
        console.log("outer func:  this.foo = " + this.foo);
        console.log("outer func:  self.foo = " + self.foo);
        (function() {
            console.log("inner func:  this.foo = " + this.foo);
            console.log("inner func:  self.foo = " + self.foo);
        }());
    }
};
myObject.func();
```

- [x] Answer: The above code will output the following to the console:
```js
outer func:  this.foo = bar
outer func:  self.foo = bar
inner func:  this.foo = undefined
inner func:  self.foo = bar
```
In the outer function, both this and self refer to myObject and therefore both can properly reference and access foo.

In the inner function, though, this no longer refers to myObject. As a result, this.foo is undefined in the inner function, whereas the reference to the local variable self remains in scope and is accessible there.