### What is the purpose of dir method of console object
The console.dir() is used to display an interactive list of the properties of the specified JavaScript object as JSON.

```js
const user = { name: "John", id: 1, city: "Delhi" };
console.dir(user);
```

### What is a strict mode in javascript
Strict Mode is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a “strict” operating context. This way it prevents certain actions from being taken and throws more exceptions. The literal expression "use strict"; instructs the browser to use the javascript code in the Strict mode.

### What are the list of cases error thrown from non-strict mode to strict mode
When you apply `'use strict'`; syntax, some of the below cases will throw a SyntaxError before executing the script

- When you use Octal syntax
    `var n = 022;`
- Using with statement
- When you use delete operator on a variable name
- Using eval or arguments as variable or function argument name
- When you use newly reserved keywords
- When you declare a function in a block
    ```js
        if (someCondition) {
        function f() {}
        }
    ```

Hence, the errors from above cases are helpful to avoid errors in development/production environments.


### How do you declare strict mode
The strict mode is declared by adding "use strict"; to the beginning of a script or a function. If declared at the beginning of a script, it has global scope.

```js
"use strict";
x = 3.14; // This will cause an error because x is not declared
```
and if you declare inside a function, it has local scope
```js
x = 3.14; // This will not cause an error.
myFunction();

function myFunction() {
  "use strict";
  y = 3.14; // This will cause an error
}
```

### What is a service worker
A Service worker is basically a script (JavaScript file) that runs in the background, separate from a web page and provides features that don't need a web page or user interaction. Some of the major features of service workers are Rich offline experiences(offline first web application development), periodic background syncs, push notifications, intercept and handle network requests and programmatically managing a cache of responses.

### 1. Name the types of functions

**The types of function are:**

- **Named** - These type of functions contains name at the time of definition. For Example:
```js
    function display()
    {
    document.writeln("Named Function");
    }
    display();
```

- **Anonymous** - These type of functions doesn't contain any name. They are declared dynamically at runtime.
```js
    var display=function()
    {
    document.writeln("Anonymous Function");  
    }
    display();
```

### 2. Is javascript a statically typed or a dynamically typed language?

JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during **run-time** in contrast to a statically typed language, where the type of a variable is checked during **compile-time**.


### 3. What are global variables?

Global variables are those that are available throughout the length of the code without any scope. The var keyword is used to declare a local variable but if you omit it then it will become global variable

```js 
    msg = "Hello"; // var is missing, it becomes global variable
```

### 4. What are the differences between undeclared and undefined variables

Below are the major differences between undeclared(not defined) and undefined variables,

- **undeclared**

  - These variables do not exist in a program and are not declared
  - If you try to read the value of an undeclared variable, then a runtime error is encountered

- **undefined**

  - These variables declared in the program but have not assigned any value
  - If you try to read the value of an undefined variable, an undefined value is returned.

### 5. How do you assign default values to variables
You can use the logical or operator || in an assignment expression to provide a default value. The syntax looks like as below,

```js
    var a = b || c;
```
As per the above expression, variable 'a 'will get the value of 'c' only if 'b' is falsy (if is null, false, undefined, 0, empty string, or NaN), otherwise 'a' will get the value of 'b'.

### 6. What is the precedence order between local and global variables
A local variable takes precedence over a global variable with the same name. Let's see this behavior in an example.
```js
    var msg = "Good morning";
    function greeting() {
    msg = "Good Evening";
    console.log(msg); // Good Evening
    }
    greeting();
```

### 7. Is const variable makes the value immutable
No, the const variable doesn't make the value immutable. But it disallows subsequent assignments(i.e, You can declare with assignment but can't assign another value later)
```js
    const userList = [];
    userList.push("John"); // Can mutate even though it can't re-assign
    console.log(userList); // ['John']
```



## nullish coalescing operator

### 8. What is nullish coalescing operator (??)?
It is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand. This can be contrasted with the logical OR (||) operator, which returns the right-hand side operand if the left operand is any falsy value, not only null or undefined.
```js
    console.log(null ?? true); // true
    console.log(false ?? true); // false
    console.log(undefined ?? true); // true
```
### What is the output of below console statement with unary operator
Let's take console statement with unary operator as given below,

`console.log(+"Hello");`
The output of the above console log statement returns NaN. Because the element is prefixed by the unary operator and the JavaScript interpreter will try to convert that element into a number type. Since the conversion fails, the value of the statement results in NaN value.

## Conditional

### 9. What is a conditional operator in javascript
The conditional (ternary) operator is the only JavaScript operator that takes three operands which acts as a shortcut for if statements.

```js
    var isAuthenticated = false;
    console.log(
    isAuthenticated ? "Hello, welcome" : "Sorry, you are not authenticated"
    ); //Sorry, you are not authenticated
```

### 10. Can you apply chaining on conditional operator
Yes, you can apply chaining on conditional operators similar to if … else if … else if … else chain. The syntax is going to be as below,
```js
function traceValue(someParam) {
  return condition1
    ? value1
    : condition2
    ? value2
    : condition3
    ? value3
    : value4;
}

// The above conditional operator is equivalent to:

function traceValue(someParam) {
  if (condition1) {
    return value1;
  } else if (condition2) {
    return value2;
  } else if (condition3) {
    return value3;
  } else {
    return value4;
  }
}
```