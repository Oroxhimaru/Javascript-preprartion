# 🔥 Start karte hain: **Scope + Lexical Scoping (foundation for closures)**

---

# 🔥 🔹 1. Scope kya hota hai?

👉 Scope = “where variables are accessible”

📌 Roman Urdu:
“variable kahan use ho sakta hai aur kahan nahi”

---

# 🔥 Types of Scope

## 1. Global Scope

```js
let a = 10;

function test() {
  console.log(a);
}
```

👉 a sab jaga accessible hai

---

## 2. Function Scope

```js
function test() {
  let a = 10;
}

console.log(a); // ❌ error
```

👉 sirf function ke andar accessible

---

## 3. Block Scope (let/const)

```js
if (true) {
  let x = 10;
}

console.log(x); // ❌ error
```

---

# 🔥 🔹 2. Lexical Scope (VERY IMPORTANT 💀)

👉 Lexical scope = “code jahan likha gaya hai, wahan se access decide hota hai”

📌 Roman Urdu:
“function jahan define hua hai, wahi se variables access karega”

---

# 🔥 Example

```js
function outer() {
  let a = 10;

  function inner() {
    console.log(a);
  }

  inner();
}
```

👉 Output:

```
10
```

---

# 🧠 WHY?

👉 inner function ko pata hai ke uska parent scope outer hai

---

# 🔥 KEY RULE 💀

👉 Inner function can access outer variables
👉 But outer cannot access inner variables

---

# ❌ Example (reverse)

```js
function outer() {
  function inner() {
    let a = 10;
  }

  console.log(a); // ❌ error
}
```

---

# 🔥 REAL INTERVIEW TRICK 💀

```js
function outer() {
  let a = 10;

  return function inner() {
    console.log(a);
  };
}

const fn = outer();
fn();
```

👉 Output:

```
10
```

---

# 🧠 WHY THIS WORKS?

👉 Because of lexical scope + closure (next topic 💀)

---

# 🔥 GOLDEN INTERVIEW LINE

👉 “Lexical scope means inner functions have access to variables of their outer scope based on where they are defined, not where they are called.”

---

# 🎯 CHECKPOINT

Agar tum samajh gaye:

✔ scope types
✔ global vs function vs block
✔ lexical scope rule
✔ inner access outer
✔ basic nested functions

👉 then tum ready ho **Closures 💀🔥**
