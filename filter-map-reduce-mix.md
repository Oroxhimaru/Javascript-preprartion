
---

# 🧠 GOLDEN RULE (VERY IMPORTANT)

👉 Har question me pehle yeh decide karo:

1. **Filter?** (kaun se data chahiye)
2. **Map?** (data ka shape change karna hai?)
3. **Reduce?** (final single result banana hai?)

👉 Order mostly hota hai:

```
filter → map → reduce
```

---

# 🔥 REAL INTERVIEW QUESTIONS (COMBO)

---

# ❓ Q1: Adults ke names

```js id="l8tpn3"
const users = [
  { name: "Ali", age: 20 },
  { name: "Ahmed", age: 17 },
  { name: "Bilal", age: 25 }
];
```

👉 Task:
“Sirf adults ke names lao”

---

### ✔ Thinking:

* filter → age > 18
* map → name

---

### ✔ Solution:

```js id="v1f0h4"
const result = users
  .filter(u => u.age > 18)
  .map(u => u.name);
```

👉 Output:

```
["Ali", "Bilal"]
```

---

# ❓ Q2: Total price of expensive items

```js id="dcjc9t"
const products = [
  { name: "Phone", price: 500 },
  { name: "Laptop", price: 1500 },
  { name: "Mouse", price: 50 }
];
```

👉 Task:
“price > 1000 ka total nikalo”

---

### ✔ Thinking:

* filter → expensive
* reduce → total

---

### ✔ Solution:

```js id="yikvxz"
const total = products
  .filter(p => p.price > 1000)
  .reduce((acc, p) => acc + p.price, 0);
```

👉 Output:

```
1500
```

---

# ❓ Q3: Active users ke emails

```js id="k1nv9s"
const users = [
  { email: "a@gmail.com", active: true },
  { email: "b@gmail.com", active: false }
];
```

---

### ✔ Thinking:

* filter → active
* map → email

---

### ✔ Solution:

```js id="1mvgpk"
const emails = users
  .filter(u => u.active)
  .map(u => u.email);
```

---

# ❓ Q4: Total quantity of items

```js id="9eukxh"
const cart = [
  { name: "A", qty: 2 },
  { name: "B", qty: 3 }
];
```

---

### ✔ Thinking:

* reduce only (no filter/map needed)

---

### ✔ Solution:

```js id="8t9qjz"
const totalQty = cart.reduce(
  (acc, item) => acc + item.qty,
  0
);
```

---

# ❓ Q5: Names of expensive products

```js id="hj0z1r"
const products = [
  { name: "Phone", price: 500 },
  { name: "Laptop", price: 1500 }
];
```

---

### ✔ Thinking:

* filter → price > 1000
* map → name

---

### ✔ Solution:

```js id="qqqwzc"
const result = products
  .filter(p => p.price > 1000)
  .map(p => p.name);
```

---

# ❓ Q6: Count active users

```js id="wxgp2e"
const users = [
  { active: true },
  { active: false },
  { active: true }
];
```

---

### ✔ Thinking:

* filter → active
* length OR reduce

---

### ✔ Solution 1:

```js id="dqdl8x"
const count = users.filter(u => u.active).length;
```

---

### ✔ Solution 2 (reduce):

```js id="85m76h"
const count = users.reduce(
  (acc, u) => u.active ? acc + 1 : acc,
  0
);
```

---

# ❓ Q7: Flatten + filter

```js id="1pdsv9"
const arr = [[1,2],[3,4],[5]];
```

👉 even numbers only

---

### ✔ Thinking:

* flatten
* filter

---

### ✔ Solution:

```js id="m9z2k6"
const result = arr
  .flat()
  .filter(n => n % 2 === 0);
```

---

# ❓ Q8: Group + transform (ADVANCED 💀)

```js id="z5f6gk"
const users = [
  { name: "Ali", role: "admin" },
  { name: "Ahmed", role: "user" },
  { name: "Bilal", role: "admin" }
];
```

---

### ✔ Thinking:

* reduce → grouping

---

### ✔ Solution:

```js id="xv1u3l"
const hassan = users.reduce((acc,cur) => {
    if(!acc[cur.role]){
        acc[cur.role] = []
    }
    acc[cur.role].push(cur.name)
    return acc
},{})
```

👉 Output:

```
{
  admin: ["Ali", "Bilal"],
  user: ["Ahmed"]
}
```

---

# ❓ Q9: Search + transform

```js id="y7kz4j"
const products = [
  { name: "Phone" },
  { name: "Laptop" },
  { name: "Phone Cover" }
];
```

👉 search "phone"

---

### ✔ Solution:

```js id="48ynvf"
const result = products
  .filter(p => p.name.toLowerCase().includes("phone"))
  .map(p => p.name);
```

---

# ❓ Q10: Total revenue (REAL BACKEND 💀)

```js id="oxwd0d"
const orders = [
  { price: 100, qty: 2 },
  { price: 50, qty: 4 }
];
```

---

### ✔ Thinking:

* reduce → total

---

### ✔ Solution:

```js id="wt6qzu"
const revenue = orders.reduce(
  (acc, o) => acc + o.price * o.qty,
  0
);
```

---

# 🔥 FINAL INTERVIEW STRATEGY

Jab bhi question aaye:

👉 Step 1: “Mujhe kya chahiye?”

* kuch items → filter
* shape change → map
* ek value → reduce

👉 Step 2: Combine karo

---

# 🧠 FINAL VERDICT

Agar tum:

✔ filter + map combo
✔ filter + reduce combo
✔ direct reduce
✔ real-world logic

kar sakte ho →

👉 **Tum JS array methods me interview-ready ho 💀🔥**

---
