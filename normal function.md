

---

# 🔥 🔹 Function kya hota hai?

👉 Function = reusable block of code

📌 “Write once, use many times”

---

# 🔹 Basic Syntax

```js id="bwx0es"
function greet() {
  console.log("Hello");
}
```

👉 Call:

```js id="pkw80l"
greet();
```

---

# 🔥 🔹 Parameters vs Arguments (IMPORTANT)

```js id="5r8tbo"
function greet(name) {
  console.log(name);
}

greet("Ali");
```

### 📌 Difference:

* `name` → parameter
* `"Ali"` → argument

💀 VERY COMMON interview question

---

# 🔥 🔹 Return keyword

```js id="70j2l1"
function add(a, b) {
  return a + b;
}

const result = add(2, 3);
```

---

# 🔥 IMPORTANT

## ❌ console.log != return

```js id="v0g9cf"
function add(a, b) {
  console.log(a + b);
}
```

👉 return kuch nahi kar raha


👉 ✔ YES, bilkul sahi samjha tumne.

---

## 🧠 Difference:

### `console.log()`

👉 sirf screen pe print karta hai
👉 value ko bahar/send nahi karta

---

### `return`

👉 function se value **wapas bhejta hai**
👉 taake aage logic me use ho sake

---

## 🔍 Example:

### ❌ console.log only

```js id="8xbpwf"
function add(a, b) {
  console.log(a + b);
}

const result = add(2, 3);

console.log(result); // undefined
```

👉 kyun?
👉 function ne kuch return nahi kiya

---

### ✅ return

```js id="l9h91r"
function add(a, b) {
  return a + b;
}

const result = add(2, 3);

console.log(result); // 5
```

👉 ab value function se bahar aa gayi

---

## ⚡ One-line yaad:

👉 **console.log = display**
👉 **return = send value back for further logic** 👍


---

# 🔥 Function Flow (VERY IMPORTANT)

```js id="z5x8tf"
function test() {
  console.log("A");
  return;
  console.log("B");
}
```

👉 Output:

```id="6ch39f"
A
```

📌 return ke baad code nahi chalta

---

# 🔥 🔹 Function Declaration Hoisting 💀

```js id="iy1j8r"
sayHi();

function sayHi() {
  console.log("Hi");
}
```

👉 Works ✅

📌 Function declarations hoist hoti hain

---

# 🔥 Function Scope

```js id="v5efm7"
function test() {
  let x = 10;
}

console.log(x);
```

👉 ❌ error

📌 Function ke andar ka variable bahar accessible nahi

---

# 🔥 LOCAL vs GLOBAL SCOPE

```js id="q6mq8g"
let globalVar = "Hello";

function test() {
  let localVar = "Hi";
}
```

---

# 🔥 REAL INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Sum function

```js id="0gcvf0"
function add(a, b) {
  return a + b;
}
```

---

# ❓ Q2: Even/Odd checker

```js id="kcx3m4"
function isEven(num) {
  return num % 2 === 0;
}
```

---

# ❓ Q3: Find max

```js id="l5ukb1"
function max(a, b) {
  return a > b ? a : b;
}
```

---

# ❓ Q4: Reverse string

```js id="kzt9c1"
function reverse(str) {
  return str.split("").reverse().join("");
}
```

💀 VERY COMMON

---

# ❓ Q5: Count vowels

```js id="7w5hns"
function countVowels(str) {
  let count = 0;

  for (let char of str.toLowerCase()) {
    if ("aeiou".includes(char)) {
      count++;
    }
  }

  return count;
}
```

---

# 🔥 INTERVIEW TRAPS

---

## ❌ Trap 1: Missing return

```js id="f62r4k"
function add(a, b) {
  a + b;
}

console.log(add(2,3));
```

👉 Output:

```id="6qfj4z"
undefined
```

---

## ❌ Trap 2: Function hoisting confusion

```js id="jmvb0y"
hello();

var hello = function() {
  console.log("Hi");
};
```

👉 ❌ error

📌 function expression hoist nahi hoti fully

(we’ll cover deeply later)

---

## ❌ Trap 3: Return object

```js id="s5w8ui"
function test() {
  return
  {
    name: "Ali"
  };
}
```

👉 Output:

```id="bnuhza"
undefined
```

📌 automatic semicolon insertion 😵

✔ Correct:

```js id="3bm8nl"
function test() {
  return {
    name: "Ali"
  };
}
```

Yeh JS ka famous trap hai 😵
Difference **newline** ki wajah se aa raha hai.

---

## ❌ Wrong:

```js id="xg0eq7"
function test() {
  return
  {
    name: "Ali"
  };
}
```

👉 JS internally isko aise samajhta hai:

```js id="v5s8ei"
function test() {
  return; // semicolon automatically laga 😵
  
  {
    name: "Ali"
  };
}
```

👉 to function yahin khatam
👉 output = `undefined`

---

# ✅ Correct:

```js id="2ct60r"
function test() {
  return {
    name: "Ali"
  };
}
```

👉 ab object same line pe hai
👉 JS samajh gaya ke object return karna hai

---

## 🧠 Roman Urdu:

👉 `return` ke baad next line me chale gaye
👉 JS ne auto `;` laga diya
👉 isliye kuch return nahi hua

---

## ⚡ One-line yaad:

👉 **return ke baad object same line pe likho** 👍


---

# 🔥 DEFAULT PARAMETERS

```js id="aqfpfv"
function greet(name = "Guest") {
  return `Hello ${name}`;
}
```

---

# 🔥 REST PARAMETERS (IMPORTANT)

```js id="iyx3cc"
function sum(...nums) {
  return nums.reduce((a,b) => a+b, 0);
}
```

👉 accepts multiple arguments

👉 Tum almost sahi ho 👍
Problem yeh hai:

```js id="s2h9xz"
add(arr)
```

👉 yahan poora array **ek single argument** ban raha hai.

---

## 🔍 Tumhara function:

```js id="fq0m6k"
function add(...array)
```

👉 `...array` rest operator hai
👉 yeh arguments ko collect karta hai

---

## ❌ Tum kya bhej rahe ho:

```js id="6h48r0"
add(arr)
```

👉 actual:

```js id="33rzkf"
array = [[1,2,3,4]]
```

👉 nested array ban gaya 😵

---

# ✅ Correct:

```js id="qub8mg"
add(...arr)
```

👉 ab:

```js id="6hmgdk"
array = [1,2,3,4]
```

---

## ✅ Full correct code:

```js id="4s0u2q"
const arr = [1,2,3,4];

function add(...array){
  return array.reduce((acc,cur) => acc + cur, 0);
}

console.log(add(...arr));
```

👉 ✔ Haan, is case me answer same ayega.

---

## 🧠 Kyun?

Tum directly array bhej rahe ho:

```js id="nr7wpm"
add(arr)
```

👉 aur function ek normal parameter le raha hai:

```js id="lp8f5x"
function add(array)
```

👉 to:

```js id="q4j22r"
array = [1,2,3,4]
```

✔ perfectly fine

---

# 🔥 Difference kab aata hai?

## Without rest:

```js id="79k1ol"
function add(array)
```

👉 sirf **1 value** expect karta hai (yahan array)

---

## With rest:

```js id="9u2h0g"
function add(...array)
```

👉 multiple arguments collect karta hai

```js id="5x7x0g"
add(1,2,3,4)
```

👉 ban jata hai:

```js id="b8d6e4"
array = [1,2,3,4]
```

---

## ⚡ Simple rule:

👉 normal param → single value
👉 rest param (`...`) → multiple values collect into array 👍


---

## 🧠 Roman Urdu:

👉 function me `...` = collect
👉 function call me `...` = spread/unpack

---

## ⚡ One-line yaad:

👉 **definition me ... = collect**
👉 **call me ... = spread** 👍


---

# 🔥 CALLBACK FUNCTION (IMPORTANT PREVIEW)

```js id="l22yyz"
function greet(name, callback) {
  console.log(name);
  callback();
}
```

📌 VERY IMPORTANT future topic

---

# 🔥 FUNCTION vs METHOD

```js id="x8zq4s"
function test() {}
```

👉 function

```js id="mkwfw9"
obj.test()
```

👉 method

the function work with object and classes are called method

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “Functions are first-class citizens in JavaScript”

👉 “Function declarations are hoisted”

👉 “Return immediately stops execution”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ function declaration
✔ parameters vs arguments
✔ return keyword
✔ scope
✔ hoisting basics
✔ default/rest params
✔ common coding questions

samajh gaye →

👉 then you are **INTERVIEW READY for normal functions 🔥**

---



