
# JavaScript Functions

### Lesson objectives

- Be able to declare functions
- Understand the three types of functions
- Understand the differences between the types of functions

### Basic Syntax:

```
function validFunctionName(parameter) {
  return statement;
}
```

### A Function Declaration

The function declaration (function statement) defines a function with the specified parameters.
```
function calcRectArea(width, height) {
  return width * height;
}

console.log(calcRectArea(5, 6));
// expected output: 30
```
A function can have multiple parameters or no parameters at all. 
In the following example, bark does not list any parameter names
```
function bark() {
  return "woof-woof";
}
bark(); //   woof-woof
```

### Function Expression

A Function Expression defines a named or anonymous function. 
An anonymous function is a function that has no name.

```
var fullName = function(firstName, lastName) {
 return firstName + " " + lastName;
}
fullName("Peter", "Nguyen"); // Peter Nguyen
```

### ES6 Arrow Function 

An Arrow Function Expression is a shorter syntax for writing function expressions. 
Arrow functions do not create their own value.

We can write the arrow function in multiple ways:

First: like a regular function expression but has an arrow (=>) key.

```
const double = (value) => {
  return value * 2
}
double(10); // 20
```

Second: Omit the return keyword

```
const double2 = value => value * 2;
double2(10); // 20
```

Third: If our function has no parameter

```
const noise = () => console.log("Pling");
noise(); // Pling
```

Fourth: If we have two or more parameters, you must use parenthesis

```
const addAll = (x, y, z) => x + y + z;
addAll(10, 20, 30); // 60
```

Fifth: We can use default values in our parameters

```
const multiply = (a = 2, b = 3, c = 1) => a * b * c;
multiply(2, 2, 2); // 8
multiply(2, 2);    // 4
multiply(3);       // 9
multiply();        // 6
```

Remember that the return keyword can only be used INSIDE of a function