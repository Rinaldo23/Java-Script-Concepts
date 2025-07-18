Hoisting in JavaScript is a behavior where variable and function declarations are conceptually moved to the top of their respective scopes during the compilation phase, before the code execution begins. This means that declarations are processed before any code within that scope is run. [1, 2, 3, 4]  

Key aspects of hoisting: 

• Variable Hoisting (with var): 
	• Variables declared with var are hoisted to the top of their function or global scope. 
	• Only the declaration is hoisted, not the initialization. 
    - This means a var variable accessed before its assignment will have a value of undefined. [5]  

    console.log(myVar); // Output: undefined
    var myVar = 10;
    console.log(myVar); // Output: 10

• Variable Hoisting (with let and const): 
	• Variables declared with let and const are also hoisted, but they are not initialized. [5, 6]  
	• They enter a "Temporal Dead Zone" (TDZ) from the beginning of their block scope until their declaration line is reached. Accessing them within the TDZ will result in a ReferenceError. 

    // console.log(myLet); // Throws ReferenceError: Cannot access 'myLet' before initialization
    let myLet = 20;
    console.log(myLet); // Output: 20

• Function Hoisting: 
	• Function declarations are fully hoisted, meaning both the function name and its definition are moved to the top of their scope. 
	• This allows you to call a function before its declaration in the code. 

    greet(); // Output: Hello!
    function greet() {
        console.log("Hello!");
    }

• Function Expressions: 
	• Function expressions (where a function is assigned to a variable) are not fully hoisted like function declarations. Only the variable declaration is hoisted, following the rules of var, let, or const. 

    // sayHi(); // Throws TypeError: sayHi is not a function (if using var) or ReferenceError (if using let/const)
    var sayHi = function() {
        console.log("Hi there!");
    };
    sayHi(); // Output: Hi there!

In summary: Hoisting is a fundamental concept in JavaScript that influences how code behaves, particularly concerning the order of declarations and their accessibility. Understanding it is crucial for avoiding unexpected errors and writing predictable JavaScript code. 
