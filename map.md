# Map

map() kya hota hai?

map() ek array method hai jo:

👉 Har element par function chalata hai

👉 Aur naya array return karta hai (original ko change nahi karta)

🔹 Basic Syntax

array.map((value, index, array) => {
  return newValue;
});


🔹 Simple Example
const nums = [1, 2, 3, 4];

const doubled = nums.map(num => num * 2);

console.log(doubled);

👉 Output:

[2, 4, 6, 8]

raha
🔹 Important Points (Interview Gold ⚡)

✔ Always new array return karta hai

✔ Original array mutate nahi hota

✔ Loop internally chalta hai

✔ Har iteration me callback function call hota hai


(question ask to gpt:

Haan bilkul 👍

### 1. `num` ki jagah kuch bhi likh sakte ho?

Haan, `num` sirf ek **parameter name** hai. Tum kuch bhi meaningful naam rakh sakte ho.

Example:

```js
nums.map(x => x * 2)
nums.map(value => value * 2)
nums.map(item => item * 2)
nums.map(abc => abc * 2)
```

Sab same kaam karenge ✅
Bas condition yeh hai ke jo naam tum arrow function me use karo, **andar bhi wahi naam use karo**.

---

### 2. `(num => num * 2)` ka matlab kya hai?

Roman Urdu me simple samajh lo:

👉 Yeh ek **function** hai jo har element pe chalega
👉 `num` = current value (array ka ek item)
👉 `num * 2` = us value ko double kar do

Matlab:

* pehle `1` aayega → `1 * 2 = 2`
* phir `2` → `2 * 2 = 4`
* phir `3` → `3 * 2 = 6`
* phir `4` → `4 * 2 = 8`

Final:

```js
[2, 4, 6, 8]
```

---

### 3. ✔ "Loop internally chalta hai" ka kya matlab hai?

Iska matlab:

👉 Tumne manually `for` loop nahi likha
👉 Lekin `map()` khud andar hi andar loop chala raha hota hai

Jaise yeh:

```js
nums.map(num => num * 2)
```

Actually internally kuch aisa ho raha hota hai:

```js
for (let i = 0; i < nums.length; i++) {
  // har item pe function chal raha hai
}
```

Roman Urdu:
👉 `map()` khud hi array ke har element pe ghoomta hai (loop lagata hai)
👉 aur har item pe tumhara function apply karta hai

---

### Short summary:

* `num` = koi bhi naam ho sakta hai
* `num => num * 2` = har value ko double karne wala function
* `map()` = khud hi loop chala ke har element process karta hai

---

)


🔹 map() vs forEach() (Very Important)
Feature	map()	forEach()
Return value	New array	undefined
Use case	Transformation	Side effects
Chainable	Yes	No

👉 Example:

const arr = [1,2,3];

const result = arr.forEach(num => num * 2);

console.log(result); // undefined ❌

Objects ke sath map
const users = [
  { name: "Ali", age: 20 },
  { name: "Ahmed", age: 25 }
];

const names = users.map(user => user.name);

console.log(names);

👉 Output:

["Ali", "Ahmed"]

🔹 Real World Example (Frontend)
const products = [
  { id: 1, price: 100 },
  { id: 2, price: 200 }
];

const updated = products.map(p => ({
  ...p,
  price: p.price + 50
}));

👉 Yeh React me bohot use hota hai 🔥

(Great question 🔥 — yeh thoda tricky part hota hai JS ka, interview me bhi poocha jata hai.

---

## 1. Yeh `({})` kyun use kiya?

```js
p => ({
  ...p,
  price: p.price + 50
})
```

👉 Yeh actually **object return karne ke liye** use hota hai.

### Important rule:

Arrow function me:

* `{}` = **function body**
* `({})` = **object return**

---

### ❌ Agar tum aise likho:

```js
p => {
  ...p,
  price: p.price + 50
}
```

👉 Yeh **object nahi return karega**, balkay JS confuse ho jata hai
👉 Isko wo "block of code" samajhta hai, object nahi

---

### ✅ Isliye correct way:

```js
p => ({
  ...p,
  price: p.price + 50
})
```

👉 Round brackets `()` batate hain:
"bhai yeh object hai, return karo"

---

### Short Roman Urdu:

👉 `()` lagaya → object return ho raha hai
👉 `()` nahi lagaya → JS samjhega yeh function body hai

---

## 2. Pehle kyun nahi use kiya?

```js
num => num * 2
```

👉 Kyun ke yeh **simple expression** hai (object nahi hai)
👉 JS automatically return kar deta hai

---

## 3. Yeh `...p` kya hai? (IMPORTANT 🔥)

👉 Isko kehte hain **Spread Operator**

Roman Urdu me:
👉 "p object ke saare properties copy kar do"

---

### Example:

```js
p = { id: 1, price: 100 }
```

```js
{
  ...p
}
```

👉 ban gaya:

```js
{ id: 1, price: 100 }
```

---

### Tumhara code:

```js
({
  ...p,
  price: p.price + 50
})
```

👉 Step by step:

1. `...p` → purana object copy

```js
{ id: 1, price: 100 }
```

2. `price: p.price + 50` → overwrite kar diya

```js
{ id: 1, price: 150 }
```

---

### Final output:

```js
[
  { id: 1, price: 150 },
  { id: 2, price: 250 }
]
```

---

## 4. Simple samajh lo:

* `...p` → purana data copy karo
* `price: ...` → update karo
* `({})` → object return karo

---

## Interview style line 🔥

👉 "We use parentheses `()` in arrow function to return an object, because without it JavaScript treats `{}` as function body."

---

)

Chaining (Advanced)
const nums = [1,2,3,4];

const result = nums
  .map(n => n * 2)
  .filter(n => n > 4);

console.log(result);

result: [ 6, 8 ]


Callback Parameters Deep Dive
arr.map((value, index, array) => {})
value → current element
index → position
array → original array


🔹 Callback Parameters Deep Dive
arr.map((value, index, array) => {})
value → current element
index → position
array → original array
🔹 Edge Cases
1. Empty array
[].map(x => x * 2); // []
2. Return na karo
const result = [1,2,3].map(num => {
  num * 2;
});

console.log(result);

👉 Output:

[undefined, undefined, undefined]


📌 Kyun?
→ return nahi kiya

(
  Short aur seedha 👇

```js
const result = [1,2,3].map(num => {
  num * 2;
});
```

👉 Tumne `{}` use kiya hai → iska matlab **function body** hai
👉 Aur andar `return` nahi likha

Isliye har iteration pe **undefined return ho raha hai**

---

### Isliye output:

```js
[undefined, undefined, undefined]
```

---

### Fix ✅

Ya to:

```js
num => num * 2
```

Ya:

```js
num => {
  return num * 2;
}
```

)


3. Sparse array
const arr = [1, , 3];

arr.map(x => x * 2);

👉 Empty slots skip ho jate hain



Common Interview Questions 🔥
❓ Q1: map kya karta hai?

👉 Array ke har element ko transform karta hai aur new array return karta hai.

❓ Q2: map aur forEach me difference?

👉 map return karta hai, forEach nahi.

❓ Q3: kya map original array change karta hai?

👉 ❌ Nahi (immutable)

❓ Q4: kya map async hota hai?

👉 ❌ Nahi (sync hota hai)

❓ Q5: map ko async ke sath use?
const data = [1,2,3];

const result = data.map(async num => {
  return num * 2;
});

console.log(result);

👉 Output:

[Promise, Promise, Promise]

📌 Solve:

const final = await Promise.all(result);
console.log(final)

answer:
[ Promise { 2 }, Promise { 4 }, Promise { 6 } ]
[ 2, 4, 6 ]


❓ Q6: map ko object pe use kar sakte?

👉 Direct nahi ❌
👉 Object ko array me convert karo:

Object.keys(obj).map(...)
❓ Q7: map vs filter?

👉 map → transform
👉 filter → condition

❓ Q8: map vs reduce?

👉 map → simple transformation
👉 reduce → complex aggregation

❓ Q9: can we break map?

👉 ❌ Nahi
👉 break/continue use nahi hota

Kyun?

👉 map() ek high-level function hai
👉 Yeh internally loop chala raha hota hai
👉 Tum us loop ko control nahi kar sakte (jaise break / continue)

Example (galat soch):
[1,2,3,4].map(num => {
  if (num === 2) break; // ❌ error
  return num * 2;
});

👉 Yeh chalega hi nahi

Roman Urdu:

👉 map() apna loop khud chalata hai
👉 Tum beech me usay rok nahi sakte

Agar break chahiye ho to?

👉 for loop use karo:

for (let num of [1,2,3,4]) {
  if (num === 2) break;
  console.log(num);
}

❓ Q10: map chaining kyun use hoti?

👉 Clean aur readable code ke liye

Without chaining ❌
const nums = [1,2,3];

const doubled = nums.map(n => n * 2);
const filtered = doubled.filter(n => n > 2);

👉 2 steps, extra variables

With chaining ✅
const result = [1,2,3]
  .map(n => n * 2)
  .filter(n => n > 2);

👉 Ek flow me sab kaam
👉 Easy to read


Roman Urdu:

👉 chaining = ek ke baad ek operations likhna
👉 code chhota + samajhne me easy
👉 unnecessary variables kam ho jate hain

Real-life soch:

👉 Data aaya API se
👉 pehle transform karo (map)
👉 phir filter karo (filter)
👉 sab ek chain me ho jata hai 🔥


🔹 Real Interview Trick Question ⚠️
const arr = [1,2,3];

const result = arr.map(parseInt);

console.log(result);

👉 Output:

[1, NaN, NaN]

📌 Reason:
parseInt(value, index) use karta hai
index radix ban jata hai 😵

Radix kya hota hai?

👉 Radix = number system (base)

Roman Urdu:
👉 radix matlab kis base me number ko read karna hai

parseInt ka kaam
parseInt(value, radix)

👉 Matlab:
"iss value ko iss base me number samajh ke convert karo"

8
🔥 Ab tumhara question easy ho gaya
[1,2,3].map(parseInt)

👉 map kya deta hai?

(value, index)
Step by step:
1st:
parseInt(1, 0)

👉 radix 0 = default (10)
👉 result = 1 ✅

2nd:
parseInt(2, 1)

👉 radix 1 ❌ (invalid) = 👉 JavaScript me valid radix range hoti hai: 2 se le kar 36 tak
👉 result = NaN

3rd:
parseInt(3, 2)

👉 radix 2 = binary
👉 binary me sirf 0,1 hota hai only digit 1 and 0 for binanary system 
👉 "3" allowed nahi ❌
👉 result = NaN

🔹 Final output:
[1, NaN, NaN]

🔥 REAL INTERVIEW CODING QUESTIONS (MAP BASED)


❓ Q1: Extract names from users
const users = [
  { id: 1, name: "Ali" },
  { id: 2, name: "Ahmed" }
];

👉 Output:

["Ali", "Ahmed"]
✔ Solution:
const names = users.map(user => user.name);
❓ Q2: Add new field (age + 1)
const users = [
  { name: "Ali", age: 20 },
  { name: "Ahmed", age: 25 }
];

👉 Output: age + 1

✔ Solution:
const updated = users.map(user => ({
  ...user,
  age: user.age + 1
}));
❓ Q3: Convert numbers to strings
const nums = [1,2,3];

👉 Output:

["1","2","3"]
✔ Solution:
const result = nums.map(String);
❓ Q4: Multiply index with value (Tricky)
const nums = [10, 20, 30];

👉 Output:

[0, 20, 60]
✔ Solution:
const result = nums.map((num, index) => num * index);
❓ Q5: Format API response
const apiData = [
  { first: "Ali", last: "Khan" },
  { first: "Ahmed", last: "Raza" }
];

👉 Output:

["Ali Khan", "Ahmed Raza"]
✔ Solution:
const fullNames = apiData.map(
  user => `${user.first} ${user.last}`
);
❓ Q6: Conditional mapping

👉 If age > 18 → "Adult" else "Minor"

const users = [
  { name: "Ali", age: 17 },
  { name: "Ahmed", age: 22 }
];
✔ Solution:
const result = users.map(user => ({
  ...user,
  status: user.age > 18 ? "Adult" : "Minor"
}));
❓ Q7: Extract nested values
const data = [
  { user: { name: "Ali" } },
  { user: { name: "Ahmed" } }
];
✔ Solution:
const names = data.map(item => item.user.name);
❓ Q8: Convert array of objects to single array
const data = [
  { skills: ["JS", "React"] },
  { skills: ["Node", "Mongo"] }
];

👉 Output:

["JS","React","Node","Mongo"]
✔ Solution:
const result = data.map(d => d.skills).flat();

🔹 Step 1: map() kya kar raha hai?
const result = data.map(d => d.skills)

👉 map() har object se sirf skills pick kar raha hai

Output banega:
[
  ["JS", "React"],
  ["Node", "Mongo"]
]

👉 Roman Urdu:

har object se skills nikali
result ab array of arrays ban gaya
🔹 Step 2: flat() kya karta hai?
.flat()

👉 flat() nested arrays ko ek single array me convert karta hai

Example:
[
  ["JS", "React"],
  ["Node", "Mongo"]
].flat()

👉 Output:

["JS", "React", "Node", "Mongo"]
🧠 Roman Urdu:

👉 flat() = andar ke arrays ko bahar nikaal deta hai
👉 simple list bana deta hai

🔥 Final flow samajh lo:
map() → skills nikal ke array of arrays banaya
flat() → sab ko merge karke single array bana diya


❓ Q9: Dangerous question (missing return)
const arr = [1,2,3];

const result = arr.map(num => {
  num * 2;
});

👉 Output:

[undefined, undefined, undefined]

📌 Interview trick: “Why undefined?”

❓ Q10: parseInt trap (VERY COMMON)
["1","2","3"].map(parseInt);

👉 Output:

[1, NaN, NaN]

📌 Reason:
map passes (value, index)
parseInt treats index as radix 😵


🔥 “Map remaining gap” (sirf 3% advanced edge cases)

Ye tum optional samajh lo, but senior interviewer kabhi kabhi pooch leta hai:

1. map vs memory/performance
map internally new array create karta hai
large datasets me extra memory use hoti hai


## 🔥 1. `map()` memory me kya karta hai?

👉 `map()` **new array banata hai**

Example:

```js id="p1x7aa"
const arr = [1,2,3];
const result = arr.map(x => x * 2);
```

👉 Memory me yeh hota hai:

* `arr` (original array)
* `result` (new array created)

---

## 🧠 Key point:

👉 `map()` **original array ko change nahi karta**
👉 balkay **new copy banata hai**

Is concept ko kehte hain:
👉 **immutability**

---

## 🔥 2. Performance / memory issue kya hai?

### Small data:

👉 koi issue nahi 👍

### Large data (100k / 1M records):

👉 problem yeh hoti hai:

* extra memory use hoti hai (new array)
* CPU time bhi lagta hai transform karne me

---

### Example:

```js id="y8m3qz"
bigArray.map(x => x * 2)
```

👉 memory:

* original array
* * new array same size

👉 yani **double memory usage temporarily**

---

## 🧠 Roman Urdu:

👉 map har element ko process karke **naya array banata hai**
👉 isliye memory extra lagti hai
👉 large data me heavy ho sakta hai

---

## 🔥 3. Interview smart line:

👉 “map is not in-place; it creates a new array, so it has O(n) time and O(n) extra space complexity.”

---

## ⚡ Kab use karein?

✔ jab:

* data transform karna ho
* original data safe rakhna ho

❌ avoid jab:

* sirf loop chahiye
* no need of new array (use `for` or `forEach`)

---

## 🧠 One-line yaad:

👉 **map = transform + new array + extra memory**

---

2. sparse arrays behavior
[, , 3].map(x => x * 2)

👉 empty slots skip hotay hain

(ye rare hai but trick question hota hai)


3. chaining order confusion
arr.map().filter().map()

👉 order matters (map first changes structure)



