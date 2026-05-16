# 🔥 🔹 Hoisting (INTERVIEW PERFECT VERSION)

## 🔥 Basic Idea (tumne sahi bola 👍)

👉 JavaScript pehle code run nahi karta,
pehle **memory creation phase** hota hai.

📌 Is phase me:

* variables declare ho jate hain
* functions memory me store ho jate hain

---

# 🔥 1. var hoisting

```js id="a1b2c3"
console.log(a);
var a = 10;
```

👉 Output:

```js id="out1"
undefined
```

---

## 🧠 WHY?

JS internally:

```js id="d4e5f6"
var a = undefined;
console.log(a);
a = 10;
```

---

# 🔥 2. let / const hoisting (IMPORTANT 💀)

```js id="g7h8i9"
console.log(a);
let a = 10;
```

👉 ❌ Error:

```
ReferenceError: Cannot access 'a' before initialization
```

---

## 🧠 WHY?

👉 let/const bhi hoist hote hain
BUT:

# 💀 Temporal Dead Zone (TDZ)

---

# 🔥 TDZ kya hota hai?

👉 Time between:

* variable memory me exist karta hai
* but usable nahi hota

📌 Roman Urdu:
“variable memory me hai, lekin use karne se pehle block locked hai”

---

# 🔥 3. const behavior

```js id="j1k2l3"
console.log(a);
const a = 5;
```

👉 same TDZ error 💀

---

# 🔥 4. Function hoisting (VERY IMPORTANT)

```js id="m4n5o6"
sayHi();

function sayHi() {
  console.log("Hello");
}
```

👉 Output:

```
Hello
```

---

## 🧠 WHY?

👉 function pura ka pura memory phase me store ho jata hai

---

# 🔥 BUT (IMPORTANT TRAP 💀)

```js id="p7q8r9"
sayHi();

var sayHi = function() {
  console.log("Hi");
};
```

👉 ❌ Error / undefined function call

---

## 🧠 WHY?

```js id="s1t2u3"
var sayHi = undefined;
sayHi();
```

---

# 🔥 INTERVIEW SUMMARY (PERFECT ANSWER)

👉 “Hoisting is JavaScript’s behavior where variable and function declarations are moved to the top of their scope during the memory creation phase.”

---

# 🔥 KEY DIFFERENCE TABLE

| Type     | Hoisted | Value at start | Access before declare |
| -------- | ------- | -------------- | --------------------- |
| var      | yes     | undefined      | yes                   |
| let      | yes     | TDZ            | no                    |
| const    | yes     | TDZ            | no                    |
| function | yes     | full function  | yes                   |

---

# 🔥 REAL INTERVIEW TRAPS 💀

---

## ❌ Trap 1

```js id="v4w5x6"
console.log(a);
let a = 10;
```

👉 TDZ error (NOT undefined)

---

## ❌ Trap 2

```js id="y7z8a9"
console.log(typeof a);
let a;
```

👉 ❌ ReferenceError (TDZ again)

---

## ❌ Trap 3

```js id="b1c2d3"
function test() {
  console.log(a);
  var a = 5;
}
```

👉 undefined

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “var is hoisted with undefined initialization.”

👉 “let and const are hoisted but remain in Temporal Dead Zone.”

👉 “Function declarations are fully hoisted with their body.”

---

# 🎯 FINAL CHECK

Agar tum:

✔ var hoisting
✔ let/const TDZ
✔ function hoisting
✔ function expression issue
✔ internal memory concept

samajh gaye →

👉 then **HOISTING COMPLETE 💀🔥**

---
