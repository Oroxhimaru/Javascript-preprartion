# 🔥 🔹 async/await kya hota hai?

👉 Promises ko cleaner aur readable way me handle karne ka syntax

📌 Roman Urdu:
“Promise ko synchronous style me likhna”

---

# 🔥 Before async/await (Promise style)

```js id="a1b2c3"
fetchData()
  .then(data => {
    console.log(data);
  })
  .catch(err => {
    console.log(err);
  });
```

---

# 🔥 After async/await

```js id="d4e5f6"
async function getData() {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (err) {
    console.log(err);
  }
}
```

📌 cleaner 💀

---

# 🔥 🔹 `async` kya karta hai?

👉 Function ko Promise bana deta hai

---

# 🔥 Example

```js id="g7h8i9"
async function test() {
  return "Hello";
}
```

---

## Internally:

```js id="j1k2l3"
Promise.resolve("Hello");
```

---

# 🔥 Output

```js id="m4n5o6"
test().then(console.log);
```

👉 Output:

```id="0kzj2q"
Hello
```

---

# 🔥 🔹 `await` kya karta hai?

👉 Promise complete hone tak wait karta hai

📌 BUT:
👉 sirf async function ke andar use hota hai

---

# 🔥 Example

```js id="p7q8r9"
function fetchData() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("Data received");
    }, 2000);
  });
}
```

---

## Using await

```js id="s1t2u3"
async function getData() {
  const data = await fetchData();

  console.log(data);
}

getData();
```

---

# 🧠 Roman Urdu Flow

1. `await fetchData()`
2. JS wait karega promise resolve hone tak
3. phir next line chalegi

---

# 🔥 ERROR HANDLING (VERY IMPORTANT 💀)

## ✔ try/catch

```js id="v4w5x6"
async function getData() {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (err) {
    console.log("Error:", err);
  }
}
```

---

# 🔥 INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Basic async function

```js id="y7z8a9"
async function hello() {
  return "Hi";
}
```

---

# ❓ Q2: Delay function

```js id="b1c2d3"
function wait() {
  return new Promise(resolve => {
    setTimeout(resolve, 1000);
  });
}
```

---

## Use:

```js id="e4f5g6"
async function run() {
  await wait();
  console.log("Done");
}
```

---

# ❓ Q3: Fetch user

```js id="h7i8j9"
async function getUser() {
  const response = await fetch("/api/user");

  const data = await response.json();

  console.log(data);
}
```

💀 VERY COMMON

---

# 🔥 MULTIPLE AWAITS (IMPORTANT)

```js id="k1l2m3"
const a = await task1();
const b = await task2();
```

👉 sequential execution

---

# 🔥 PERFORMANCE OPTIMIZATION 💀

## ❌ Slow

```js id="n4o5p6"
const a = await task1();
const b = await task2();
```

👉 waits one by one

---

## ✔ Faster

```js id="q7r8s9"
const [a, b] = await Promise.all([
  task1(),
  task2()
]);
```

💀 VERY IMPORTANT INTERVIEW POINT

---

# 🔥 INTERVIEW TRAPS 💀

---

## ❌ Trap 1: await outside async

```js id="t1u2v3"
await fetchData();
```

👉 ❌ error

---

## ❌ Trap 2: forgetting await

```js id="w4x5y6"
const data = fetchData();

console.log(data);
```

👉 Promise object 😵

---

## ✔ Correct

```js id="z7a8b9"
const data = await fetchData();
```

---

## ❌ Trap 3: async function always returns Promise

```js id="c1d2e3"
async function test() {
  return 5;
}
```

👉 actually:

```js id="f4g5h6"
Promise.resolve(5)
```

---

## ❌ Trap 4: async in forEach 💀💀

```js id="i7j8k9"
arr.forEach(async item => {
  await process(item);
});
```

👉 ❌ dangerous

📌 forEach wait nahi karta

---

## ✔ Correct

```js id="l1m2n3"
for (let item of arr) {
  await process(item);
}
```

---

# 🔥 async/await vs Promise.then

| Feature           | then/catch | async/await |
| ----------------- | ---------- | ----------- |
| readability       | medium     | high        |
| chaining          | yes        | cleaner     |
| error handling    | catch      | try/catch   |
| looks synchronous | no         | yes         |

---

# 🔥 REAL WORLD USE CASES

---

## ✔ API requests

```js id="o4p5q6"
const data = await fetch("/api");
```

---

## ✔ Database queries

```js id="r7s8t9"
const users = await User.find();
```

---

## ✔ File operations

```js id="u1v2w3"
const file = await readFile();
```

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “async functions always return Promises.”

👉 “await pauses execution until the Promise resolves.”

👉 “async/await improves readability over Promise chaining.”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ async keyword
✔ await keyword
✔ try/catch
✔ Promise relationship
✔ Promise.all optimization
✔ async loop issue
✔ common traps

samajh gaye →

👉 then you are **INTERVIEW READY for async/await 💀🔥**

---