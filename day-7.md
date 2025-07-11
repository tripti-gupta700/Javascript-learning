# 🚀 Day 7 - JavaScript

## ⏳ Duration
3 hours of focused learning.

## 📚 What I learned today


### ⚡ Advanced Promise Combinators
- **`Promise.any`:** resolves as soon as any promise fulfills, ignores rejects unless all fail.
- **`Promise.race`:** returns first settled promise (fulfilled or rejected).
- **`Promise.allSettled`:** waits for all to settle, returns array of results `{ status, value | reason }`.

### 🔥 Error handling in async/await
- Using `try/catch` inside async functions for clean control.
- Adding fallback values when API fails.

async function getData(){
  try {
    let res = await fetch(url);
    return await res.json();
  } catch (err) {
    console.error("Failed:", err);
    return []; // fallback
  }
}
🧑‍💻 IIFE (Immediately Invoked Function Expressions)
Runs as soon as it is defined.

Useful for creating private scopes.

(function(){
  console.log("Runs immediately");
})();
🔗 Memoization with closures
Used closures to cache results of expensive calls.

function memoizedAdd() {
  let cache = {};
  return function(num) {
    if (cache[num]) {
      console.log("From cache");
      return cache[num];
    }
    console.log("Calculating...");
    let result = num + 10;
    cache[num] = result;
    return result;
  }
}
const add = memoizedAdd();
add(5); // Calculating
add(5); // From cache
🧩 Array flat & flatMap
flat() flattens nested arrays.

flatMap() maps & flattens by one level.


[1, [2,3], [4, [5]]].flat(2); // [1,2,3,4,5]
["hello", "world"].flatMap(x => x.split("")) 
// ["h","e","l","l","o","w","o","r","l","d"]
🔍 Object utilities with reduce
Transforming object into another using Object.entries + reduce.

const obj = { a: 1, b: 2 };
const doubled = Object.entries(obj).reduce((acc, [key, val]) => {
  acc[key] = val * 2;
  return acc;
}, {});
// { a: 2, b: 4 }
✅ Key takeaways
Learned to write robust async code using multiple promise combinators.

Practiced advanced closures for memoization and data privacy.

Explored functional utilities on both arrays and objects.

Strengthened knowledge of execution nuances like IIFE and this differences.


#30DaysOfCode #JavaScript #Promises #Closures #Memoization #IIFE #FunctionalProgramming
