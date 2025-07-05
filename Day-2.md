#  Day 2 - JavaScript

##  Duration
2 hours of focused study.

##  What I learned

###  `let` and `const`
- Learned about `let` and `const` variable declarations.
- Unlike `var`, `let` and `const` are **block scoped**.
- Their declarations are hoisted but remain uninitialized until the code execution phase, which is why they exist in the **Temporal Dead Zone (TDZ)**.

###  Temporal Dead Zone (TDZ)
- The time between the hoisting of a variable (`let` / `const`) and its actual initialization.
- Accessing these variables before initialization results in a **ReferenceError**.
- 
console.log(a); // ReferenceError
let a = 10;

🌐 **Scope of Variables**
var is function-scoped or globally scoped. Can be attached to the global object (window.varName).

let and const are block scoped, meaning they are only accessible within the enclosing {}.

They do not become properties of the global object.
var x = 5;
console.log(window.x); // 5
let y = 10;
console.log(window.y); // undefined

 **Block Scope, Shadowing & Illegal Shadowing**
**Block scope:** Variables declared with let and const are only accessible inside the block they are defined in.

**Shadowing:** When a variable in a local scope (like inside a function or block) has the same name as one in an outer scope. The local variable “shadows” the outer one.
let a = 100;
{
    let a = 10; // shadows outer `a`
    console.log(a); // 10
}
console.log(a); // 100

**Illegal shadowing:** Happens when trying to declare a var in a block scope that would override a let or const from an outer scope, leading to unexpected behavior.


let b = 20;
{
    var b = 30; // illegal shadowing (will throw error in strict mode)
}

🚀 Lexical Block Scope
Lexical block scope means the scope is determined at the time of writing the code (lexically), not during execution.

🔥** Closures**
**Closures are functions that remember their lexical environment even after the outer function has finished execution.**

If a function is defined inside another function, it closes over the outer function's variables.

function outer() {
    let count = 0;
    function inner() {
        count++;
        console.log(count);
    }
    return inner;
}

const fn = outer();
fn(); // 1
fn(); // 2
Even though outer() has finished executing, inner() still has access to count due to closure.

🚀 Uses of Closures
Module design patterns: to encapsulate private data.

Currying: returning functions to build up arguments.

Once functions: ensure a function runs only once.

Memoization: caching results to improve performance.

Maintaining state in async world: like with setTimeout, event listeners.

Iterators & Generators.

💡 Reflection
Today I covered some heavy but essential topics.
✅ Now I can clearly explain block scope, temporal dead zone, and closures to anyone.
Looking forward to exploring setTimeout, and solving interview questions on closures tomorrow.

📝 Next Up
setTimeout, asynchronous closures, and closure-based interview problems.

