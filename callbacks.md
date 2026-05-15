Yeh concept samajh liya to baqi sab (Promises, async/await, event loop) bohot easy ho jayega.

---

# 🔥 🔹 Callback kya hota hai?

👉 Callback = **function jo kisi aur function ko argument ke taur pe diya jaye**

📌 Roman Urdu:
“Ek function doosre function ko diya jaye taake wo baad me call ho”

---

# 🔥 Simple Example

```js id="a1b2c3"
function greet(name) {
  console.log("Hello " + name);
}

function processUser(callback) {
  const name = "Ali";
  callback(name);
}

processUser(greet);
```

---

# 🧠 Flow samjho:

1. `processUser()` call hua
2. usne `greet` function receive kiya
3. baad me call kiya `callback(name)`

---

# 🔥 REAL LIFE EXAMPLE

👉 Imagine:

* order place karo
* payment complete ho
* phir email send ho

```js id="d4e5f6"
function paymentDone() {
  console.log("Payment Done");
}

function order(callback) {
  console.log("Order placed");
  callback();
}

order(paymentDone);
```

---

# 🔥 WHY CALLBACKS EXIST? (IMPORTANT 💀)

👉 JS synchronous language hai, but async behavior chahiye hota hai:

* API calls
* timers
* file reading

👉 callbacks help us handle “later execution”

---

# 🔥 setTimeout is BEST EXAMPLE

```js id="g7h8i9"
console.log("Start");

setTimeout(() => {
  console.log("After 2 sec");
}, 2000);

console.log("End");
```

---

## Output:

```
Start
End
After 2 sec
```

---

# 🧠 Roman Urdu Flow:

👉 JS ne setTimeout ko background me bhej diya
👉 baqi code chal gaya
👉 time complete hua → callback run hua

---

# 🔥 CALLBACK TYPES

---

## 1. Synchronous Callback

```js id="j1k2l3"
function process(callback) {
  callback();
}
```

👉 instantly execute

---

## 2. Asynchronous Callback 💀

```js id="m4n5o6"
setTimeout(() => {
  console.log("Async callback");
}, 1000);
```

👉 later execute

---

# 🔥 CALLBACK HELL 💀💀 (VERY IMPORTANT INTERVIEW TOPIC)

👉 jab callbacks nested ho jate hain

---

```js id="p7q8r9"
login(user, function() {
  getProfile(function() {
    getPosts(function() {
      getComments(function() {
        console.log("Done");
      });
    });
  });
});
```

---

# 😵 Problem:

✔ code unreadable
✔ hard to debug
✔ maintain karna mushkil

📌 isko kehte hain: **Callback Hell**

---

# 🔥 REAL INTERVIEW QUESTION 💀

👉 “What is callback hell?”

✔ Answer:
👉 nested callbacks causing unreadable code structure

---

# 🔥 HOW TO FIX CALLBACK HELL?

👉 Promises (next topic 💀)

---

# 🔥 REAL WORLD USE CASES

---

## ✔ Event listeners

```js id="s1t2u3"
button.addEventListener("click", () => {
  console.log("Clicked");
});
```

---

## ✔ API calls (old style)

```js id="v4w5x6"
fetchData(function(result) {
  console.log(result);
});
```

---

## ✔ Timers

```js id="y7z8a9"
setInterval(() => {
  console.log("Running...");
}, 1000);
```

---

# 🔥 INTERVIEW TRAPS 💀

---

## ❌ Trap 1: Callback not executed

```js id="b1c2d3"
function test(callback) {
  callback;
}
```

👉 ❌ WRONG (function call missing)

---

## ✔ Correct

```js id="e4f5g6"
function test(callback) {
  callback();
}
```

---

## ❌ Trap 2: Confusing sync vs async

```js id="h7i8j9"
console.log("A");

setTimeout(() => console.log("B"), 0);

console.log("C");
```

👉 Output:

```
A
C
B
```

💀 VERY IMPORTANT INTERVIEW QUESTION

---

# 🔥 CALLBACK vs NORMAL FUNCTION

| Feature     | Normal Function | Callback           |
| ----------- | --------------- | ------------------ |
| Called by   | you             | another function   |
| Timing      | immediate       | later / controlled |
| Async use   | no              | yes                |
| flexibility | low             | high               |

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “A callback is a function passed as an argument to another function to be executed later.”

👉 “Callbacks are the foundation of asynchronous programming in JavaScript.”

👉 “Too many nested callbacks lead to callback hell, which is solved using Promises.”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ callback concept
✔ sync vs async callback
✔ setTimeout understanding
✔ callback hell
✔ real world usage
✔ common traps

samajh gaye →

👉 then you are **STRONG in Callbacks 💀🔥**
