# filter

Perfect 👍 ab hum **JavaScript ka `filter()`** complete interview level pe cover karte hain — same style: Roman Urdu + coding + traps + interview questions.

---

# 🔹 `filter()` kya hota hai?

👉 `filter()` array ka method hai jo:

* condition check karta hai
* aur **sirf matching elements ka new array return karta hai**

---

# 🔹 Syntax

```js id="f7xq1a"
array.filter((value, index, array) => {
  return condition;
});
```

---

# 🔹 Basic Example

```js id="k2q9vn"
const nums = [1, 2, 3, 4, 5];

const even = nums.filter(num => num % 2 === 0);

console.log(even);
```

👉 Output:

```js id="v9l2pm"
[2, 4]
```

const nums = [1, 2, 3, 4, 5];

const even = nums.filter(num => num % 1 === 0);

console.log(even);

[ 1, 2, 3, 4, 5 ]

---

# 🔹 Important Concept

✔ filter = condition based selection
✔ new array return hota hai
✔ original array change nahi hota
✔ jo condition **true** ho sirf wo elements aate hain

---

# 🔥 map vs filter (VERY IMPORTANT)

| Feature   | map               | filter                   |
| --------- | ----------------- | ------------------------ |
| Purpose   | transform         | select                   |
| Return    | same length array | filtered (smaller/equal) |
| Condition | optional          | required                 |
| Output    | modified values   | original values          |

---

# 🔹 Example difference

```js id="2m7zrw"
const nums = [1,2,3,4];

nums.map(n => n > 2);
nums.filter(n => n > 2);
```

👉 map output: becuase map transform data and give full array that's why here it is shown as true and false

```js id="l1xq9k"
[false, false, true, true]
```

👉 filter output:

```js id="q9c3nb"
[3, 4]
```

---

# 🔥 REAL INTERVIEW CODING QUESTIONS

---

# ❓ Q1: Even numbers filter

```js id="x7tq9p"
const nums = [1,2,3,4,5,6];
```

### ✔ Solution:

```js id="p2m8vn"
const even = nums.filter(n => n % 2 === 0);
```

---

# ❓ Q2: Adults only (objects)

```js id="m9k2zx"
const users = [
  { name: "Ali", age: 17 },
  { name: "Ahmed", age: 22 }
];
```

👉 age > 18

### ✔ Solution:

```js id="b3n7qk"
const adults = users.filter(user => user.age > 18);
```

---

# ❓ Q3: Remove falsy values

```js id="r4t9wx"
const arr = [0, 1, false, 2, "", 3, null];
```

### ✔ Solution:

```js id="s8v2mn"
const clean = arr.filter(Boolean);
```
Boolean(value)  : 👉 Boolean ek function hai jo value ko true / false me convert karta hai 
hai

👉 filter() har element ko check karta hai
👉 jo true return kare, usko rakhta hai
👉 jo false ho, usko hata deta hai

👉 Output:

```js id="t5x9qp"
[1, 2, 3]
```
🔥 Falsy values kya hoti hain?

JavaScript me yeh 6 falsy values hoti hain:

false
0
""
null
undefined
NaN

---

# ❓ Q4: Search by name

```js id="c8p1xz"
const users = ["Ali", "Ahmed", "Adeel"];
```

👉 names starting with "A"

### ✔ Solution:

```js id="n7m4qk"
const result = users.filter(name => name.startsWith("A"));
```

🔹 startsWith("A") kya karta hai?

👉 Yeh check karta hai ke string "A" se start ho rahi hai ya nahi
"Alice".startsWith("A") // true
"Bob".startsWith("A")   // false

---

# ❓ Q5: Filter expensive products

```js id="v1q9tp"
const products = [
  { name: "Phone", price: 500 },
  { name: "Laptop", price: 1500 }
];
```

### ✔ Solution:

```js id="k6x2mn"
const expensive = products.filter(p => p.price > 1000);
```

---

# ❓ Q6: Multiple conditions

👉 age > 18 AND name starts with A

```js id="z3n8qp"
const users = [
  { name: "Ali", age: 20 },
  { name: "Bilal", age: 25 },
  { name: "Ahmed", age: 17 }
];
```

### ✔ Solution:

```js id="q9v1mn"
const result = users.filter(
  u => u.age > 18 && u.name.startsWith("A")
);
```

---

# ❓ Q7: Remove undefined/null

```js id="t2k7zx"
const arr = [1, undefined, 2, null, 3];
```

### ✔ Solution:

```js id="p5m9qk"
const clean = arr.filter(item => item != null);
```

---

# ❓ Q8: Filter nested data

```js id="n1v8tp"
const data = [
  { user: { active: true } },
  { user: { active: false } }
];
```

### ✔ Solution:

```js id="x7q3mn"
const activeUsers = data.filter(d => d.user.active);
```

---

# 🔥 FILTER TRAPS (INTERVIEW FAVORITE)

---

## ❌ Trap 1: forgetting return

```js id="m8q1tp"
const result = [1,2,3].filter(n => {
  n > 1;
});
```

👉 Output:

```js id="k2v9xn"
[]
```

📌 Reason:
no return → undefined → false

---

## ❌ Trap 2: truthy/falsy confusion

```js id="p9x2mn"
[0,1,2].filter(n => n);
```

👉 Output:

```js id="t7q1kp"
[1, 2]
```

---

## ❌ Trap 3: object condition mistake

```js id="v3n8qp"
users.filter(user => user.age)
```

👉 This is WRONG if age = 0 or missing logic needed

✅ Correct (jab sirf check karna ho ke age exist karti hai):
users.filter(user => user.age !== undefined)

✅ Ya agar valid age chahiye (>= 0):
users.filter(user => user.age >= 0)

👉 direct user.age likhne se falsy values bhi remove ho jati hain


---

# 🔥 INTERVIEW QUESTIONS THEORY

---

## ❓ Q1: filter kya karta hai?

👉 condition match hone wale elements return karta hai

---

## ❓ Q2: filter original array change karta hai?

👉 ❌ nahi

---

## ❓ Q3: filter vs map?

👉 map = transform
👉 filter = select

---

## ❓ Q4: can we break filter?

👉 ❌ nahi

---

## ❓ Q5: filter empty array?

```js id="kq9xmn"
[].filter(x => x)
```

👉 []

---

# 🔥 REAL WORLD USE CASE

👉 API data filtering:

```js id="n7q2tp"
const activeUsers = apiData.filter(user => user.isActive);
```

👉 search functionality:

```js id="m1v8xn"
items.filter(item => item.name.includes("phone"));
```
👉 includes = "andar yeh word hai ya nahi check karo"

---

# 🧠 FINAL SUMMARY

✔ filter = selection tool
✔ condition-based array reduction
✔ always returns new array
✔ heavily used in backend + frontend APIs
✔ interview favorite method

---

---

# 🔥 What’s still remaining in `filter()`?

## 1. ⚠️ Real interview pattern (IMPORTANT)

Interviewer rarely sirf simple filter deta hai.
Wo bolta hai:

👉 “filter + map use karo”
👉 “filter + reduce combo”

Example:

```js
const users = [
  { name: "Ali", age: 20 },
  { name: "Ahmed", age: 17 },
  { name: "Bilal", age: 25 }
];
```

👉 Task:
“Sirf adults ke **names** return karo”

### ✔ Solution:

```js
const result = users
  .filter(u => u.age > 18)
  .map(u => u.name);
```

📌 Ye **VERY COMMON interview question** hai

---

## 2. ⚠️ Negation filtering (trap)

👉 “remove items”

```js
const nums = [1,2,3,4,5];
```

👉 remove even numbers

```js
const result = nums.filter(n => n % 2 !== 0);
```

📌 interviewer check karta hai:
tum logic ulta kar sakte ho ya nahi

---

## 3. ⚠️ Complex condition thinking

```js
products.filter(p => p.price > 1000 && p.inStock)
```

👉 multiple conditions confidently likhna

---

## 4. ⚠️ Includes / search pattern (VERY COMMON)

```js
const users = ["Ali", "Ahmed", "Bilal"];
```

👉 search "ah"

```js
users.filter(name =>
  name.toLowerCase().includes("ah")
);
```

📌 ye real-world + interview dono me aata hai

---

## 5. ⚠️ Duplicate removal (important)

```js
const arr = [1,2,2,3,4,4];
```

### ✔ Solution:

```js
const unique = arr.filter(
  (item, index, self) => self.indexOf(item) === index
);
```

📌 ye thoda advanced hai but poocha jata hai

---

## 🔥 Pehle yeh samjho:

```js
arr.filter((item, index, self) => ...)
```

👉 `filter` ke 3 params hote hain:

* `item` → current value
* `index` → current index
* `self` → **poora array** ✅

👉 Haan, **`self` = array hi hai**

---

## 🔥 `indexOf` kya karta hai?

```js
self.indexOf(item)
```

👉 yeh batata hai:
👉 **is value ka first occurrence kis index pe hai**

---

### Example:

```js
[1,2,2,3].indexOf(2) // 1
```

👉 chahe 2 do baar ho, yeh hamesha **pehli position** deta hai

---

## 🔥 Ab main logic samjho:

```js
self.indexOf(item) === index
```

👉 matlab:
👉 “kya yeh item apni **first position** pe hai?”

---

## 🔥 Step by step:

```js
[1,2,2,3,4,4]
```

| item | index | indexOf(item) | match?   |
| ---- | ----- | ------------- | -------- |
| 1    | 0     | 0             | ✅ keep   |
| 2    | 1     | 1             | ✅ keep   |
| 2    | 2     | 1             | ❌ remove |
| 3    | 3     | 3             | ✅ keep   |
| 4    | 4     | 4             | ✅ keep   |
| 4    | 5     | 4             | ❌ remove |

---

## 🔥 Final output:

```js
[1,2,3,4]
```

---

## 🧠 Roman Urdu:

👉 `indexOf` pehli baar jahan value milti hai wo index deta hai
👉 agar current index uske barabar ho → first time hai → rakh lo
👉 warna duplicate hai → hata do

---

## ⚡ One-line yaad:

👉 **“sirf first occurrence rakho, baaki hata do”**

---

## 🔥 Bonus (modern way 👇 easier):

```js
const unique = [...new Set(arr)];
```

👉 yeh bhi same kaam karta hai 😏



---

# 🔥 FINAL INTERVIEW CHECKLIST (FILTER)

Agar tum ye sab confidently kar sakte ho:

✔ simple filtering
✔ objects filtering
✔ multiple conditions
✔ remove items (negation)
✔ filter + map combo
✔ search (includes)
✔ falsy cleanup
✔ duplicate removal logic samajh

👉 then you are **INTERVIEW READY ✅**

---

