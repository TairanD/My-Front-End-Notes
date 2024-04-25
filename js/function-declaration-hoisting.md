# Function Declaration Hoisting

In JavaScript, hoisting refers to the built-in behavior of the language through which declarations of functions, variables, 
and classes are moved to the top of their scope – all before code execution. In turn, this allows us to use functions, variables, 
and classes before they are declared.

## Declaration

In JavaScript, declarations include using:
- `function` to declare a function (including generators)
- `async function` to declare an async function (including generators)
- `class` to declare a class
- `var` to declare a variable
- `let` to declare a block-scoped variable
- `const` to declare a block-scoped, non-reassignable variable\

## Function Declaration Hoisting
Under the hood, function declarations are put into memory at compile time. As such, this makes it possible to, on 
execution, call a declared function before it is defined. For example:
```javascript
console.log(greeting()); // "Hello there!"

function greeting() {
 return "Hello there!";
}
```
In the above snippet, we are able to log the return value of invoking greeting() before that function is even defined. 
This is all due to function hoisting – a built-in behavior of JavaScript that hoists a function’s declaration and its value to the top of their scope.

*Note that this differs from invoking a function that is never declared: 
```javascript
console.log(greeting()); // ReferenceError: greeting is not defined

var greeting = function() {
  console.log("Hi!");
};
```
Since the function is never defined anywhere, the JavaScript interpreter evaluates the expression as a `ReferenceError`.
