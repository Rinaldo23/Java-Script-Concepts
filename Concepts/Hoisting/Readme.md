Here’s the updated README section with your **quick reference** added to the top, formatted for clarity and consistency:

---

## 🧠 Hoisting in JavaScript

> **Quick Reference**
> Hoisting in JavaScript is a behavior where **variable and function declarations are moved to the top of their scope before code execution**.
>
> * This allows you to use variables and functions before they are declared in the code.
> * However, only **declarations** are hoisted—**not initializations or assignments**.

---

Hoisting in JavaScript is a behavior where **variable and function declarations are conceptually moved to the top of their respective scopes** during the compilation phase—before any code is executed. This means that declarations are processed before any code within that scope runs. \[1, 2, 3, 4]

---

### 🔑 Key Aspects of Hoisting

#### 📦 Variable Hoisting (with `var`)

* Variables declared with `var` are hoisted to the top of their function or global scope.
* Only the **declaration** is hoisted, **not the initialization**.
* Accessing a `var` variable before assignment will yield `undefined`. \[5]

```js
console.log(myVar); // Output: undefined
var myVar = 10;
console.log(myVar); // Output: 10
```

---

#### 📦 Variable Hoisting (with `let` and `const`)

* `let` and `const` are also hoisted, but **they are not initialized**. \[5, 6]
* They enter a **Temporal Dead Zone (TDZ)** from the start of the block until the declaration is evaluated.
* Accessing them within the TDZ results in a `ReferenceError`.

```js
// console.log(myLet); // Throws ReferenceError
let myLet = 20;
console.log(myLet); // Output: 20
```

---

#### 🔧 Function Hoisting

* **Function declarations** are fully hoisted (both name and body).
* You can safely call the function before its declaration.

```js
greet(); // Output: Hello!
function greet() {
    console.log("Hello!");
}
```

---

#### ⚠️ Function Expressions

* **Function expressions** (assigned to variables) are not fully hoisted.
* Only the variable declaration is hoisted, following `var`, `let`, or `const` rules.

```js
// sayHi(); // Throws TypeError (with var) or ReferenceError (with let/const)
var sayHi = function() {
    console.log("Hi there!");
};
sayHi(); // Output: Hi there!
```

---

### ✅ Summary

Hoisting is a fundamental concept that affects the **order of declaration and accessibility** in your code. A solid understanding of hoisting helps you avoid unexpected behavior and write **more predictable, bug-free JavaScript**.

---

Let me know if you'd like to add a visual diagram or a comparison table as well.
