Day 4 - JavaScript

## ⏳ Duration
3 hours of intense learning.

## 🚀 What I learned today

### 🏗️ JavaScript Engine & Callstack
- The **JavaScript engine** (like V8 in Chrome) is what runs our JS code. It resides inside the **browser**.
- Inside the JS engine, there is a **Callstack**, which:
  - Holds the execution context.
  - Can execute **one piece of code at a time** (single-threaded).
  - Works on **LIFO** (Last In First Out) — meaning the most recent function pushed in is the first to be executed.

---

### ⏰ Web APIs
- JavaScript alone **doesn't have access** to things like:
  - Timers (`setTimeout`)
  - HTTP requests (`fetch`)
  - DOM manipulation
  - Local storage
- These are provided by the **browser environment** as **Web APIs**.
- When we call `setTimeout`, it’s actually handled by the browser, not by the JS engine directly.


### 🔄 Event Loop
- The **Event Loop** is like a **gatekeeper**. It keeps watching:
  - The **Callstack**
  - The **Callback Queue**
  - The **Microtask Queue**

- It continuously checks:
  1. Is the Callstack empty?  
  2. If yes, is there any task in **Microtask Queue** (like resolved promises, mutation observers)?
  3. If Microtask Queue is empty, then it checks the **Callback Queue** (like `setTimeout` callbacks, DOM events).

- It pushes the first available task into the Callstack for execution.



### 📝 Simple illustration

+-------------------------+
|     JavaScript Engine    |
|   --------------------   |
|   |     Callstack     |   |
|   --------------------   |
+-------------------------+

+-------------------------+
|        Browser          |
| ----------------------- |
| |       Web APIs      | |
| ----------------------- |
+-------------------------+

+-------------------------+
|    Callback Queue       |
+-------------------------+
|    Microtask Queue      |
+-------------------------+

(Event Loop: checks these and pushes into Callstack)
🔥 Why is this important?
Helps understand asynchronous behavior in JavaScript.

Shows why JS is non-blocking, even though it’s single-threaded.

Explains why setTimeout callbacks execute after synchronous code finishes, regardless of delay.

📝 Reflection
Understood that the Callstack can handle only one task at a time.

Learned about Web APIs that let JS do powerful things like HTTP requests and timers by providing a bridge to the outside world.

Grasped how the Event Loop orchestrates execution between the Callstack, Microtask Queue, and Callback Queue, ensuring the program runs smoothly.

🔥 Next Up
Diving deeper into Promises, async/await, and comparing how they interact with the event loop vs traditional callbacks.

