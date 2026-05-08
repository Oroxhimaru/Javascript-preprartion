
---

# 🔥 🔹 Function Expression kya hota hai?

👉 Jab function ko kisi variable me store karte hain

---

# 🔹 Basic Syntax

```js id="jlwmwu"
const greet = function() {
  console.log("Hello");
};
```

👉 Call:

```js id="jlwmwu"
greet();
```

---

# 🔥 Difference from Function Declaration

## Function Declaration

```js id="9zgvf7"
function greet() {
  console.log("Hi");
}
```

---

## Function Expression

```js id="q6qimf"
const greet = function() {
  console.log("Hi");
};
```

---

# 🔥 MOST IMPORTANT DIFFERENCE → HOISTING 💀

---

# 🔹 Function Declaration

```js id="9r8vdf"
sayHi();

function sayHi() {
  console.log("Hi");
}
```

👉 ✅ Works

---

# 🔹 Function Expression

```js id="g1g0v3"
sayHi();

const sayHi = function() {
  console.log("Hi");
};
```

👉 ❌ Error

---

# 🧠 Roman Urdu Logic

👉 Function declaration pura memory me load hota hai

👉 Function expression me:

* sirf variable hoist hota hai
* function baad me assign hota hai

---

# 🔥 Internally kya hota hai?

```js id="2cf7z0"
const sayHi = function() {}
```

JS internally:

```js id="w9j94q"
const sayHi = undefined;
```

📌 Function baad me assign hota hai

---

# 🔥 Anonymous Function (IMPORTANT)

```js id="u8a9fr"
const greet = function() {
  console.log("Hello");
};
```

👉 Function ka name nahi → anonymous function

---

# 🔥 Named Function Expression

```js id="s04w8j"
const greet = function sayHi() {
  console.log("Hello");
};
```

📌 Rare but interview me pooch sakte hain


✔ Bilkul 😄 isi liye confusion hoti hai.

---

## 🔥 Yeh code:

```js id="v1"
const test = function() {
  console.log("Hi");
};
```

👉 isme:

* yeh **function expression** bhi hai ✅
* aur andar wala function **anonymous** bhi hai ✅

---

## 🧠 Samjho:

### “Anonymous”

👉 function ka **naam hai ya nahi**?

```js id="v2"
function() {}
```

👉 no name → anonymous

---

### “Function Expression”

👉 function ko variable me store kiya ya nahi?

```js id="v3"
const test = function() {};
```

👉 variable me store hua → function expression

---

# 🔥 Realization:

👉 ek function **dono cheezein** ho sakta hai:

* anonymous
* function expression

---

# ⚡ Example breakdown:

```js id="v4"
const test = function() {};
```

| Part               | Type                |
| ------------------ | ------------------- |
| `function() {}`    | anonymous function  |
| `const test = ...` | function expression |

---

## ⚡ One-line yaad:

👉 **Anonymous = no function name**
👉 **Expression = assigned/stored somewhere** 👍


---

# 🔥 REAL INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Function expression banaao

```js id="z0ukcw"
const add = function(a, b) {
  return a + b;
};
```

---

# ❓ Q2: Multiply function

```js id="w6t3i4"
const multiply = function(a, b) {
  return a * b;
};
```

---

# ❓ Q3: Store function in variable

```js id="fytm2r"
const greet = function(name) {
  return `Hello ${name}`;
};
```

---

# 🔥 FUNCTIONS ARE FIRST-CLASS CITIZENS 💀

👉 JS me function ko:

* variable me store kar sakte
* argument bana sakte
* return kar sakte

---

# 🔥 Example

```js id="nkl9lj"
function test(fn) {
  fn();
}

test(function() {
  console.log("Hello");
});
```

📌 Ye higher-order functions ki base hai 🔥

---

# 🔥 Function Expression + Arrow Function

## Function Expression

```js id="kn7e2i"
const add = function(a, b) {
  return a + b;
};
```

---

## Arrow Version

```js id="n1bz7m"
const add = (a, b) => a + b;
```

---

# 🔥 INTERVIEW TRAPS

---

## ❌ Trap 1: Hoisting

```js id="4cvmkr"
hello();

var hello = function() {
  console.log("Hi");
};
```

👉 ❌ TypeError

📌 because:

```js id="6vq0wo"
var hello = undefined;
```

then:

```js id="v9n7an"
undefined();
```

😵

---

## ❌ Trap 2: Missing semicolon

```js id="wqgh6j"
const test = function() {}
```

📌 semicolon recommended

---

## ❌ Trap 3: Named function expression confusion

```js id="pj8ytw"
const greet = function sayHi() {
  console.log(typeof sayHi);
};
```

👉 inside accessible
👉 outside nahi

---

# 🔥 FUNCTION DECLARATION vs EXPRESSION

| Feature                | Declaration | Expression          |
| ---------------------- | ----------- | ------------------- |
| Hoisted                | fully       | partially           |
| Before definition call | yes         | no                  |
| Syntax                 | direct      | variable assignment |
| Anonymous possible     | no          | yes                 |

---

# 🔥 REAL WORLD USE CASES

---

## ✔ Callback functions

```js id="g5j26q"
button.addEventListener("click", function() {
  console.log("Clicked");
});
```

---

## ✔ Dynamic assignment

```js id="o0d0xr"
const handler = function() {};
```

---

# 🧠 GOLDEN INTERVIEW LINE

👉 “Function expressions are not fully hoisted because they behave like variables.”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ function expression syntax
✔ hoisting difference
✔ anonymous function
✔ named function expression
✔ declaration vs expression

samajh gaye →

👉 then you are **INTERVIEW READY for Function Expressions 🔥**

---

