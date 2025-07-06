# 📚 Day 3 - JavaScript

## ⏳ Duration
3 hours of focused study.

## 🚀 What I learned

### ⏱️ `setTimeout`
- `setTimeout` is used to **schedule a function to run after a specified delay** (in milliseconds).
- It is asynchronous, does not block the main thread.
- Example:
    console.log("Start");
    setTimeout(() => console.log("Runs after 2 seconds"), 2000);
    console.log("End");
    
- Output will be:
    Start
    End
    Runs after 2 seconds
 
### 🧩 Closures
- A closure is created when a function **remembers its outer lexical environment**, even after the outer function has finished executing.
- Example:

    function outer() {
        let count = 0;
        return function inner() {
            count++;
            console.log(count);
        }
    }
    const fn = outer();
    fn(); // 1
    fn(); // 2
    ```
- **Uses:** data privacy, module pattern, memoization, currying, maintaining state in async code.


### 🔄 Callback Functions
- A **callback** is a function passed as an argument to another function, to be executed later.
- Useful for **asynchronous operations** or customizing behavior.
- Examples:
   
    function greet(name, callback) {
        console.log("Hello, " + name);
        callback();
    }
    greet("Tripti", () => console.log("Goodbye!"));
   

- Example with `setTimeout`:
    setTimeout(() => console.log("Inside callback after delay"), 1000);

### 🔍 Function Types

#### ✅ Function Statement (Declaration)
- Syntax: 
    function greet() {
        console.log("Hello!");
    }

- Hoisted completely, can be called before it’s defined.

#### ✅ Function Expression
- Assigned to a variable, **not hoisted**.

    const sayHi = function() {
        console.log("Hi!");
    }
  

#### ✅ Anonymous Function
- A function **without a name**.

    setTimeout(function() {
        console.log("Hello!");
    }, 1000);
   

#### ✅ Named Function Expression
- Function expression where function itself has a name (useful for recursion or debugging).
    const add = function sum(a, b) {
        return a + b;
    }

### 🔄 Parameters vs Arguments
- **Parameters:** placeholders in function definition.
- **Arguments:** actual values passed when calling the function.
- 
function cook(dish, time) { // dish, time are parameters
    console.log(`Cooking ${dish} for ${time} min`);
}
cook("Pasta", 15); // "Pasta", 15 are arguments

**First Class Functions**
In JavaScript, functions are treated like values.

They can be passed as arguments, returned from other functions, and assigned to variables.

Example:
function sayHello() {
    console.log("Hello!");
}
function execute(fn) {
    fn();
}
execute(sayHello);

 **Arrow Functions**
A shorthand way to write functions.

Arrow functions do not have their own this context, they use this from the surrounding scope.
const multiply = (a, b) => a * b;
console.log(multiply(2, 3)); // 6
📝 Reflection
Today I learned about callbacks and how they enable asynchronous code, how setTimeout works with the event loop, revisited closures with more examples, and explored different ways to declare functions in JavaScript, their scopes and behavior.

Also cleared the difference between parameters vs arguments, understood first class functions, and wrote multiple arrow functions.

🔥 Next Up
Exploring Promises, async/await, and more on handling asynchronous JavaScript without callback hell.

