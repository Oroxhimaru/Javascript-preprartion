# 🔥 1. Memoization (SUPER SIMPLE)

👉 Concept:

# “Same input → same result → store it → reuse”

---

## 🧠 Simple idea:

Instead of recalculating:

👉 “pehle se result yaad rakh lo (cache)”

---

## ✔ Example (easy version)

```js id="m1"
function add(a, b) {
  return a + b;
}
```

👉 Problem: every time calculation repeat hoti hai

---

## ✔ Memoization idea:

```js id="m2"
function memoizedAdd() {
  let cache = {};

  return function(a, b) {
    let key = a + "," + b;

    if (cache[key]) {
      return cache[key];
    }

    let result = a + b;
    cache[key] = result;

    return result;
  };
}
```

---

## 🧠 One line:

👉 “Same input ke liye repeated calculation avoid karna”

---

# 🔥 2. Debouncing (VERY IMPORTANT FOR UI 💀)

👉 Concept:

# “User ruk jaye tab action karo”

---

## 🧠 Real life example:

👉 Search box:

* user typing… typing… typing…
* har keypress pe API call ❌

👉 instead:

* rukne ke baad call ✔

---

## ✔ Simple example:

```js id="d1"
function debounce(fn, delay) {
  let timer;

  return function(...args) {
    clearTimeout(timer);

    timer = setTimeout(() => {
      fn(...args);
    }, delay);
  };
}
```

---

## 🧠 Easy meaning:

👉 “last action ke baad wait karo, phir run karo”

---

## ✔ Use case:

* Search bar
* Input validation
* API calls on typing

---

# 🔥 3. Throttling (VERY SIMPLE DIFFERENCE)

👉 Concept:

# “Fixed interval pe sirf ek baar run karo”

---

## 🧠 Real life example:

👉 Scroll event:

* scroll 100 times/sec
* but function run once every 1 sec

---

## ✔ Simple idea:

```js id="t1"
function throttle(fn, limit) {
  let lastCall = 0;

  return function(...args) {
    let now = Date.now();

    if (now - lastCall >= limit) {
      lastCall = now;
      fn(...args);
    }
  };
}
```

---

## 🧠 Easy meaning:

👉 “har X time me sirf 1 baar execute”

---

# 🔥 DEBOUNCE vs THROTTLE (IMPORTANT 💀)

| Feature   | Debounce         | Throttle        |
| --------- | ---------------- | --------------- |
| When runs | after user stops | every interval  |
| Use case  | search input     | scroll, resize  |
| Behavior  | delay execution  | limit execution |

---

# 🧠 SUPER SIMPLE INTERVIEW ANSWER

👉 Debounce:
“Wait until user stops action, then execute.”

👉 Throttle:
“Execute at fixed intervals regardless of continuous events.”

---
