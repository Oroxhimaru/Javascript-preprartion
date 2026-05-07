
---

# 🔥 🔹 Conditionals kya hote hain?

👉 Conditionals ka matlab:

**“Agar yeh true hai to yeh karo, warna kuch aur karo”**

---

# 🔹 Basic `if / else`

```js
let age = 20;

if (age > 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

📌 Roman Urdu:

* agar condition true → if run hoga
* warna → else

---

# 🔹 `else if`

```js
let marks = 75;

if (marks > 80) {
  console.log("A");
} else if (marks > 60) {
  console.log("B");
} else {
  console.log("C");
}
```

---

# 🔥 🔹 Truthy vs Falsy (VERY IMPORTANT 💀)

👉 JS me har value true ya false treat hoti hai

### ❌ Falsy values:

```js
false
0
""
null
undefined
NaN
```

### ✔ Truthy:

👉 baaki sab (even `"0"` bhi truthy hai 😵)

---

# 🔥 Example:

```js
if ("") {
  console.log("Run");
} else {
  console.log("Not run");
}
```

👉 Output:

```
Not run
```

---

# 🔥 🔹 Ternary Operator (IMPORTANT)

👉 Short form of if/else

```js
let age = 20;

let result = age > 18 ? "Adult" : "Minor";
```

📌 Interview me poocha jata hai:
👉 “convert if/else to ternary”

---

# 🔥 🔹 `switch` statement

```js
let day = 2;

switch (day) {
  case 1:
    console.log("Mon");
    break;
  case 2:
    console.log("Tue");
    break;
  default:
    console.log("Invalid");
}
```

---

# 🔥 IMPORTANT: break ka role

```js
case 1:
  console.log("Mon");
case 2:
  console.log("Tue");
```

👉 Output:

```
Mon
Tue
```

📌 break na ho to fall-through hota hai 😵

---

# 🔥 REAL INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Check even/odd

```js
let num = 5;

if (num % 2 === 0) {
  console.log("Even");
} else {
  console.log("Odd");
}
```

---

# ❓ Q2: Max of two numbers

```js
let a = 10, b = 20;

let max = a > b ? a : b;
```

---

# ❓ Q3: Grade system

```js
if (marks >= 90) {
  console.log("A");
} else if (marks >= 70) {
  console.log("B");
} else {
  console.log("C");
}
```

---

# ❓ Q4: Login check

```js
if (user && user.isLoggedIn) {
  console.log("Welcome");
}
```

📌 real-world pattern

---

# 🔥 INTERVIEW TRAPS (VERY IMPORTANT)

---

## ❌ Trap 1: == vs ===

```js
if (5 == "5") // true
if (5 === "5") // false
```

📌 Always use `===`

---

## ❌ Trap 2: truthy confusion

```js
if ("0") {
  console.log("Run");
}
```

👉 Output:

```
Run
```

---

## ❌ Trap 3: assignment instead of comparison

```js
if (a = 5) {
  console.log("Run");
}
```

👉 ALWAYS true 😵

---

## ❌ Trap 4: null vs undefined

```js
if (null == undefined) // true
if (null === undefined) // false
```

---

## ❌ Trap 5: NaN comparison

```js
if (NaN === NaN) // false 😵
```

✔ Correct:

```js
Number.isNaN(NaN)
```

👉 `NaN` ka matlab hota hai: **invalid number**

👉 JS rule:
❌ `NaN` kabhi kisi ke equal nahi hota
👉 khud ke bhi nahi 😵

```js id="1kjql5"
NaN === NaN // false
```

---

## ⚡ One-line yaad:

👉 **“NaN is never equal to anything, even itself”**


---

# 🔥 ADVANCED PATTERNS

---

## ✔ Short circuit (VERY IMPORTANT)

```js
user && console.log(user.name);
```

```js
let name = user || "Guest";
```

Yeh **short-circuiting** hai — JS me logical operators (`&&`, `||`) values return karte hain.

---

# 🔥 1. `&&` (AND short circuit)

```js id="0tqz6w"
user && console.log(user.name);
```

👉 matlab:
👉 “agar `user` exist karta hai tabhi right side chalao”

---

## 🔍 Example:

```js id="v0x1z6"
let user = { name: "Ali" };

user && console.log(user.name);
```

👉 output:

```id="r0n79m"
Ali
```

---

### ❌ Agar:

```js id="c95nsl"
let user = null;
```

👉 to:

```js id="zk9fsc"
user && console.log(user.name);
```

👉 kuch nahi chalega
👉 error bhi nahi ayega ✅

---

## 🧠 Roman Urdu:

👉 `&&` me:

* left side false hui → right side run nahi hoti

---

# 🔥 2. `||` (OR short circuit)

```js id="mbrvhy"
let name = user || "Guest";
```

👉 matlab:
👉 “agar `user` truthy hai to user lo, warna Guest”

---

## 🔍 Example 1:

```js id="ec5v9r"
let user = "Ali";

let name = user || "Guest";

console.log(name);
```

👉 output:

```id="z3my5m"
Ali
```

---

## 🔍 Example 2:

```js id="5kx7e8"
let user = "";

let name = user || "Guest";

console.log(name);
```

👉 output:

```id="a6n6kw"
Guest
```

👉 kyun?
👉 empty string falsy hoti hai

---

# 🧠 Roman Urdu Rule:

## `&&`

👉 “agar left true hai tab right chalao”

## `||`

👉 “agar left false hai to right use karo”

---

# ⚡ One-line yaad:

👉 `&&` = conditionally run
👉 `||` = default value provide karo 👍


---

## ✔ Nullish coalescing (??)

```js
let name = userName ?? "Guest";
```

📌 difference from `||`:

* `||` → falsy check
* `??` → null/undefined only

Haan 👍 bas itna hi difference hai.

---

## 🔥 `||`

👉 **saari falsy values** check karta hai

Falsy:

```js id="dqg8t8"
false, 0, "", null, undefined
```

---

## 🔥 `??`

👉 sirf:

```js id="jlwmvq"
null ya undefined
```

check karta hai

---

# 🔍 Example:

## `||`

```js id="o07r6m"
let name = "" || "Guest";

console.log(name); // "Guest"
```

👉 empty string falsy thi

---

## `??`

```js id="cpxk4j"
let name = "" ?? "Guest";

console.log(name); // ""
```

👉 kyun?
👉 `""` null/undefined nahi hai

---

## ⚡ One-line yaad:

👉 `||` = any falsy → fallback
👉 `??` = only null/undefined → fallback 👍





---

# 🔥 REAL WORLD EXAMPLES

---

## ✔ Default value

```js
let username = input || "Guest";
```

---

## ✔ API safety

```js
if (data && data.user && data.user.name)
```

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “Always prefer === over ==”
👉 “Falsy values can cause unexpected bugs”
👉 “Short-circuiting improves readability”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ if/else confidently
✔ ternary use kar sakte ho
✔ switch + break samajh
✔ truthy/falsy clear
✔ == vs === difference
✔ short circuit + ?? samajh

👉 then you are **INTERVIEW READY 🔥**

---

# 🚀 FINAL STATUS

Ab tumne cover kar liya:

✔ Variables
✔ Data Types
✔ Conditionals
✔ Loops
✔ map/filter/reduce

👉 Yeh **core JavaScript fundamentals COMPLETE ho gaye 💀🔥**

