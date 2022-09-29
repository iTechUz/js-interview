### 1. What is the difference between == and === operators
- [x] Answer: JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables. The strict operators follow the below conditions for different types,

- Two strings are strictly equal when they have the same sequence of characters, same length, and same characters in corresponding positions.
- Two numbers are strictly equal when they are numerically equal. i.e, Having the same number value. There are two special cases in this,
  - NaN is not equal to anything, including NaN.
  - Positive and negative zeros are equal to one another.
- Two Boolean operands are strictly equal if both are true or both are false.
- Two objects are strictly equal if they refer to the same Object.
- Null and Undefined types are not equal with ===, but equal with ==. i.e, null===undefined --> false but null==undefined --> true

Some of the example which covers the above cases,
```js
    0 == false   // true
    0 === false  // false
    1 == "1"     // true
    1 === "1"    // false
    null == undefined // true
    null === undefined // false
    '0' == false // true
    '0' === false // false
    []==[] or []===[] //false, refer different objects in memory
    {}=={} or {}==={} //false, refer different objects in memory
```

### 2. What will be the output when the following code is executed? Explain.

```js
console.log(false == '0')
console.log(false === '0')
```
- [x] Answer: 
```js
true
false
```
In JavaScript, there are two sets of equality operators. The triple-equal operator === behaves like any traditional equality operator would: evaluates to true if the two expressions on either of its sides have the same type and the same value. The double-equal operator, however, tries to coerce the values before comparing them. It is therefore generally good practice to use the === rather than ==. The same holds true for !== vs !=.

### 3.  Name all JavaScript’s Boolean logical operators:

- [x] Answer: 

The AND && operator, the NOT ! operator, and the OR || operator.

The && AND operator requires both operands to be true to evaluate to true. For example:
```js
if (age >= 21 && drinksConsumed <= 10) { 
     console.log('You can drink here.')
}
```
The || OR operator requires one of the operands to be true to evaluate to true. For example:
```js
if (age >= 12 || height >= 150) { 
     console.log('You can ride the rollercoaster.') 
}
```
The ! NOT operator evaluates to true if the two operands are not equal. For example:
```js
x = 7;
y = 5;

!(x == y) // evaluates to true
```