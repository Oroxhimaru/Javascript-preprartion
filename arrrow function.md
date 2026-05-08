|
👉 difference between normal vs arrow function
👉 `this` behavior
👉 implicit return
👉 hoisting traps

---

# 🔥 🔹 Arrow Function kya hota hai?

👉 Short syntax for writing functions

---

# 🔹 Basic Syntax

## Normal Function

```js id="91zv0g"
function add(a, b) {
  return a + b;
}
```

---

## Arrow Function

```js id="lkl12g"
const add = (a, b) => {
  return a + b;
};
```

---

# 🔥 Shorter Version (IMPORTANT)

```js id="m9smdm"
const add = (a, b) => a + b;
```

📌 Single line → return automatic

---

# 🔥 Implicit Return (VERY IMPORTANT)

```js id="t1qfrr"
const square = n => n * n;
```

👉 automatically return ho raha hai

---

# 🔥 Single Parameter Shortcut

```js id="j9f36d"
const greet = name => `Hello ${name}`;
```

---

# 🔥 No Parameter

```js id="8m90st"
const test = () => "Hi";
```

---

# 🔥 Returning Object (INTERVIEW TRAP 💀)

## ❌ Wrong

```js id="5zfc0w"
const getUser = () => {
  name: "Ali"
};
```

👉 Output:

```id="1bdh4f"
undefined
```

---

## ✔ Correct

```js id="x7eh2j"
const getUser = () => ({
  name: "Ali"
});
```

📌 object ko parentheses me wrap karo

---

# 🔥 MOST IMPORTANT TOPIC → `this` DIFFERENCE 💀💀

---

# 🔹 Normal Function

```js id="3vb9rz"
const user = {
  name: "Ali",
  greet: function() {
    console.log(this.name);
  }
};

user.greet();
```

👉 Output:

```id="0x4llf"
Ali
```

---

# 🔹 Arrow Function

```js id="y92wsk"
const user = {
  name: "Ali",
  greet: () => {
    console.log(this.name);
  }
};
```

👉 Output:

```id="dn9tlu"
undefined
```

💀 VERY IMPORTANT INTERVIEW QUESTION

---

# 🧠 Roman Urdu Explanation

👉 Arrow function ka apna `this` nahi hota
👉 Wo outer scope ka `this` use karta hai

📌 Isliye object methods me arrow avoid karte hain

---

# 🔥 Arrow Function Hoisting

```js id="l9x5di"
sayHi();

const sayHi = () => {
  console.log("Hi");
};
```

👉 ❌ error

📌 kyunki yeh variable jaisa behave karta hai

---

# 🔥 REAL INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Convert normal to arrow

```js id="gn1zfw"
function multiply(a, b) {
  return a * b;
}
```

✔

```js id="04yvqx"
const multiply = (a, b) => a * b;
```

---

# ❓ Q2: Arrow function for map

```js id="s8llx6"
const nums = [1,2,3];

const doubled = nums.map(n => n * 2);
```

---

# ❓ Q3: Return object

```js id="k0h8w7"
const createUser = (name) => ({
  name
});
```

---

# 🔥 INTERVIEW TRAPS

---

## ❌ Trap 1: `this` confusion

```js id="b58m4t"
const obj = {
  name: "Ali",
  greet: () => {
    console.log(this.name);
  }
};
```

👉 undefined 😵

Chalo simple 👍

---

# 🔥 `arguments` kya hota hai?

👉 normal functions me ek special object hota hai
👉 jo saare passed arguments ko store karta hai

---

## ✅ Example:

```js id="53y7f5"
function test() {
  console.log(arguments);
}

test(1, 2, 3);
```

👉 output:

```id="a6dnz9"
[1, 2, 3]
```

---

# ❌ Arrow function me:

```js id="q5dm2s"
const test = () => {
  console.log(arguments);
};
```

👉 error 😵

---

## 🧠 Kyun?

👉 arrow functions ka:

* apna `this` nahi hota
* apna `arguments` bhi nahi hota ❌

👉 wo outer scope pe depend karti hain

---

# ✅ Correct way in arrow function:

👉 use rest operator:

```js id="8l6z32"
const test = (...args) => {
  console.log(args);
};

test(1,2,3);
```

👉 output:

```id="c70lc4"
[1,2,3]
```

---

## ⚡ One-line yaad:

👉 **Arrow functions me `arguments` nahi hota → `...args` use karo** 👍


---

## ❌ Trap 2: arguments keyword

```js id="c4w3k1"
const test = () => {
  console.log(arguments);
};
```

👉 ❌ error

📌 Arrow functions me `arguments` nahi hota

---

## ✔ Use Rest Parameter Instead

```js id="7g2a1f"
const test = (...args) => {
  console.log(args);
};
```

---

## ❌ Trap 3: constructor use

```js id="ef6nqs"
const Person = (name) => {
  this.name = name;
};

new Person("Ali");
```

👉 ❌ error

📌 Arrow functions constructors nahi ban sakte

Chalo simple Roman Urdu me 👍

---

# 🔥 Constructor kya hota hai?

👉 special function jo `new` ke sath object banata hai

---

## ✅ Normal function constructor:

```js id="kjq5ic"
function Person(name) {
  this.name = name;
}

const p1 = new Person("Ali");

console.log(p1.name); // Ali
```

👉 `new`:

* naya object banata hai
* `this` ko us object pe set karta hai

---

# ❌ Arrow function problem:

```js id="3kk8yv"
const Person = (name) => {
  this.name = name;
};

new Person("Ali");
```

👉 error 😵

---

## 🧠 Kyun?

👉 Arrow functions:

* apna `this` nahi rakhti ❌
* constructor behavior nahi hota ❌

👉 isliye:

```js id="a3mjlwm"
new Person()
```

allowed nahi

---

## ⚡ One-line yaad:

👉 **Arrow functions cannot be used with `new` because they don’t have their own `this`.** 👍


---

# 🔥 Normal vs Arrow Function

| Feature     | Normal | Arrow     |
| ----------- | ------ | --------- |
| this        | own    | inherited |
| arguments   | yes    | no        |
| constructor | yes    | no        |
| hoisting    | yes    | partial   |
| syntax      | bigger | shorter   |

---

# 🔥 REAL WORLD USE CASES

---

## ✔ Callbacks

```js id="6t00js"
arr.map(n => n * 2);
```

---

## ✔ React

```js id="6xvjxb"
const handleClick = () => {}
```

---

## ✔ Async

```js id="8cjn74"
setTimeout(() => {
  console.log("Done");
}, 1000);
```

---

# 🧠 GOLDEN INTERVIEW LINE

👉 “Arrow functions inherit `this` from their surrounding scope.”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ arrow syntax
✔ implicit return
✔ return object
✔ this difference
✔ no arguments
✔ no constructor
✔ hoisting behavior

samajh gaye →

👉 then you are **INTERVIEW READY for Arrow Functions 💀🔥**

---

