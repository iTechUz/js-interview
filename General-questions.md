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