# Day 6 - JavaScript

## ⏳ Duration
3 hours of focused learning.

## 📚 What I learned today

### 🔁 Array methods deep dive
- **forEach vs map vs filter vs reduce vs find vs some vs every**
  - `forEach`: iterates, does not return new array
  - `map`: transforms, returns new array
  - `filter`: filters by condition, returns new array
  - `reduce`: reduces to single value
  - `find`: returns first element matching condition
  - `some`: checks if **any** element passes condition
  - `every`: checks if **all** elements pass condition

- **Chained operations**
  const data = [1, 2, 3, 4];
  const result = data
    .map(x => x * 2)
    .filter(x => x > 4)
    .reduce((sum, x) => sum + x, 0);
🔀 Promise chaining & error propagation
Learned to return values in then to chain correctly.

Using .catch() for proper error bubbling.

⏳ Microtasks vs Macrotasks
Promise.then and queueMicrotask → microtask queue

setTimeout / setInterval → macrotask queue

Microtasks run before next event loop tick.

🎯 Currying functions
Example:

function multiply(a) {
  return function(b) {
    return a * b;
  };
}
const double = multiply(2);
double(5); // 10
⚡ Practical closures
Used closures to maintain state in asynchronous callbacks and timer examples.

**Key takeaways**
Solidified understanding of advanced array methods & when to use each.
Learned internal priority between microtask & macrotask queues.
Explored functional programming patterns like currying.
Practiced writing more predictable asynchronous code.
