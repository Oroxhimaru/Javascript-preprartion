

# 🔥 OBJECTS & ARRAYS MASTERY

(interview tricks + methods + patterns)

---

# 🔥 PART 1 — OBJECTS

---

# 🔹 Object kya hota hai?

👉 Key-value pair collection

```js id="a1b2c3"
const user = {
  name: "Ali",
  age: 25
};
```

---

# 🔥 Access methods

## Dot notation

```js id="d4e5f6"
user.name
```

---

## Bracket notation (IMPORTANT)

```js id="g7h8i9"
user["name"]
```

📌 Dynamic keys me useful

---

# 🔥 Dynamic Property (INTERVIEW IMPORTANT)

```js id="j1k2l3"
const key = "age";

console.log(user[key]);
```

---

# 🔥 Add property

```js id="m4n5o6"
user.city = "Karachi";
```

---

# 🔥 Delete property

```js id="p7q8r9"
delete user.age;
```

---

# 🔥 Check property

```js id="s1t2u3"
"name" in user
```

---

# 🔥 Object Methods

```js id="v4w5x6"
const user = {
  name: "Ali",
  greet() {
    console.log("Hello");
  }
};
```

---

# 🔥 Object.keys / values / entries 💀

---

## Object.keys()

```js id="y7z8a9"
Object.keys(user);
```

👉 array of keys

---

## Object.values()

```js id="b1c2d3"
Object.values(user);
```

---

## Object.entries()

```js id="e4f5g6"
Object.entries(user);
```

👉 array of key-value pairs

---

# 🔥 Loop through object

```js id="h7i8j9"
for (let key in user) {
  console.log(key, user[key]);
}
```

---

# 🔥 OBJECT INTERVIEW TRAPS 💀

---

## ❌ Trap 1: Object comparison

```js id="k1l2m3"
{} === {}
```

👉 false 😵

📌 different references

---

## ❌ Trap 2: Array is object

```js id="n4o5p6"
typeof []
```

👉 `"object"` 😵

---

## ✔ Correct check

```js id="q7r8s9"
Array.isArray(arr)
```

---

## ❌ Trap 3: Object key coercion

```js id="t1u2v3"
const obj = {};

obj[1] = "one";
obj["1"] = "hello";

console.log(obj);
```

👉 same key 😵

---

# 🔥 PART 2 — ARRAYS

---

# 🔹 Array basics

```js id="w4x5y6"
const arr = [1,2,3];
```

---

# 🔥 Important methods (INTERVIEW)

---

## push()

```js id="z7a8b9"
arr.push(4);
```

👉 end add

---

## pop()

```js id="c1d2e3"
arr.pop();
```

👉 remove last

---

## shift()

```js id="f4g5h6"
arr.shift();
```

👉 remove first

---

## unshift()

```js id="i7j8k9"
arr.unshift(0);
```

👉 add first

---

# 🔥 slice vs splice 💀

---

## slice() → non-mutating

```js id="l1m2n3"
arr.slice(1,3);
```

📌 original safe

---

## splice() → mutating 😵

```js id="o4p5q6"
arr.splice(1,2);
```

📌 original change

# 🔥 slice() vs splice() — VERY IMPORTANT

Dono names similar 😵
But behavior totally different.

---

# ✅ slice() → SAFE (non-mutating)

👉 Original array ko change nahi karta.

---

## Example

```js id="y6a1qw"
const arr = [10, 20, 30, 40, 50];

const result = arr.slice(1, 3);

console.log(result);
console.log(arr);
```

---

# 🧠 Execution

```js id="mq1c6j"
slice(start, end)
```

Means:

* start included ✔
* end NOT included ❌

So:

```js id="rk5y0f"
slice(1,3)
```

takes:

* index 1 ✔ → 20
* index 2 ✔ → 30
* stop before 3

---

# Output

```id="dr1d4r"
[20, 30]
```

Original remains same:

```id="7n5j0v"
[10, 20, 30, 40, 50]
```

---

# 💡 Memory Trick

## slice

👉 “Cut piece without damaging original”

Like pizza slice 🍕 😄

---

# ❌ splice() → DANGEROUS (mutating)

👉 Original array ko directly change karta hai.

---

## Example

```js id="q4j0lb"
const arr = [10, 20, 30, 40, 50];

const result = arr.splice(1, 2);

console.log(result);
console.log(arr);
```

---

# 🧠 Execution

```js id="h1k4ic"
splice(start, deleteCount)
```

So:

```js id="xwj2ye"
splice(1,2)
```

Means:

* start at index 1 → 20
* delete 2 items:

  * 20
  * 30

---

# Output

Removed items:

```id="0c9lza"
[20, 30]
```

Original changed 😵:

```id="j9rq8m"
[10, 40, 50]
```

---

# 🔥 HUGE DIFFERENCE

| Method   | Original Changes? | Return       |
| -------- | ----------------- | ------------ |
| slice()  | ❌ No              | copied part  |
| splice() | ✔ Yes             | removed part |

---

# 🚀 splice can ALSO add items

```js id="d1d9ki"
const arr = [10, 20, 30];

arr.splice(1, 1, 99);

console.log(arr);
```

---

# 🧠 Execution

At index 1:

* remove 1 item → 20
* insert 99

Output:

```id="wkh2wz"
[10, 99, 30]
```

---

# 💀 Interview Trap

## ❓ Why React developers avoid splice?

Because:

* splice mutates original array ❌
* React likes immutable updates ✔

So usually:

* slice
* map
* filter
* spread

preferred.

---

# 🧩 Easy Final Memory

## slice

👉 copy piece

## splice

👉 remove/change original piece 💀


---

# 🔥 find vs filter

---

## find()

```js id="r7s8t9"
arr.find(n => n > 2);
```

👉 first match

---

## filter()

```js id="u1v2w3"
arr.filter(n => n > 2);
```

👉 all matches

---

# 🔥 some vs every

---

## some()

```js id="x4y5z6"
arr.some(n => n > 2);
```

👉 any one true?

---

## every()

```js id="a7b8c9"
arr.every(n => n > 2);
```

👉 all true?

---

# 🔥 includes()

```js id="d1e2f3"
arr.includes(2);
```

---

# 🔥 join()

```js id="g4h5i6"
arr.join("-");
```

---

# 🔥 flat() (IMPORTANT)

```js id="j7k8l9"
[1,[2,[3]]].flat(2);
```

---

# 🔥 SORT TRAP 💀💀

---

## ❌ Wrong

```js id="m1n2o3"
[1, 10, 2].sort();
```

👉 Output:

```js id="p4q5r6"
[1,10,2]
```

😵 string sorting

---

## ✔ Correct

```js id="s7t8u9"
[1,10,2].sort((a,b) => a - b);
```

👉 Output:

```js id="v1w2x3"
[1,2,10]
```

🔥 Yeh JavaScript ka MOST ASKED interview concept hai.

Tum bas yeh samjho:

```js id="v7h64t"
(a, b) => a - b
```

JS ko batata hai:

> “kis value ko pehle rakhna hai”

---

# 🧠 sort() actually kya karta hai?

JS internally 2 values uthata hai:

```js id="p7m7tt"
a
b
```

phir tumhara function chalata hai:

```js id="ycvuhq"
a - b
```

Us result ke basis par decide hota hai sorting.

---

# 🔥 RULES

## If result is NEGATIVE

```js id="v8c2u2"
a - b < 0
```

👉 `a` pehle aayega

---

## If result is POSITIVE

```js id="5j2rvu"
a - b > 0
```

👉 `b` pehle aayega

---

## If result is 0

👉 order same reh sakta hai

---

# 🚀 Example Step-by-Step

```js id="g1kz4f"
[1,10,2].sort((a,b) => a - b);
```

---

## Step 1

JS compare karta hai:

```js id="01y4qo"
1 and 10
```

Function:

```js id="vn5pqf"
1 - 10 = -9
```

Negative ✔

👉 means:

```id="9x26gf"
1 pehle rahega
```

---

## Step 2

Compare:

```js id="zgr2cc"
10 and 2
```

Function:

```js id="xtokyu"
10 - 2 = 8
```

Positive ✔

👉 means:

```id="1a9y9o"
2 ko pehle lao
```

So 10 and 2 swap ho gaye.

---

# Final Output

```js id="q7qmra"
[1,2,10]
```

---

# 🔥 Descending Order

```js id="4rvq8l"
(b,a) => b - a
```

OR

```js id="cfmifq"
(a,b) => b - a
```

Example:

```js id="rmf8ew"
[1,10,2].sort((a,b) => b - a);
```

Output:

```id="4qmz0l"
[10,2,1]
```

---

# 💀 SUPER IMPORTANT

Without compare function:

```js id="jgzy5x"
[1,10,2].sort()
```

JS converts to strings 😵

```id="j2e1uv"
["1","10","2"]
```

So output becomes:

```id="3d95b6"
[1,10,2]
```

because `"10"` comes before `"2"` alphabetically.

---

# 🧩 Easy Memory Trick

## `a - b`

👉 small first (ascending)

## `b - a`

👉 big first (descending)


---

# 🔥 REVERSE TRAP

```js id="y4z5a6"
arr.reverse();
```

👉 mutates original

---

# 🔥 ARRAY INTERVIEW CODING QUESTIONS

---

# ❓ Remove duplicates

```js id="b7c8d9"
[...new Set(arr)]
```

---

# ❓ Max number

```js id="e1f2g3"
Math.max(...arr)
```

---

# ❓ Flatten array

```js id="h4i5j6"
arr.flat(Infinity)
```

`flat()` nested arrays ko seedha karta hai 🔥

---

## Example

```js id="jlwm1g"
const arr = [1, [2, 3], [4, [5]]];

console.log(arr.flat());
```

Output:

```id="lspc8h"
[1, 2, 3, 4, [5]]
```

👉 Sirf 1 level flatten hua.

---

# 💥 `Infinity`

```js id="h8v9fq"
arr.flat(Infinity)
```

Means:

> “jitni bhi nesting ho sab khatam kar do”

---

## Example

```js id="bn32hf"
const arr = [1, [2, 3], [4, [5, [6]]]];

console.log(arr.flat(Infinity));
```

Output:

```id="n90feh"
[1,2,3,4,5,6]
```

---

# 🧠 Easy meaning

## Before

```js id="7twk5q"
[1,[2,[3]]]
```

## After

```js id="8qdx9x"
[1,2,3]
```

---

# 🔥 Interview point

```js id="ytv4yc"
flat(1)
```

👉 flatten one level

```js id="d4lgj2"
flat(2)
```

👉 flatten two levels

```js id="t3zbz0"
flat(Infinity)
```

👉 flatten completely 💀


---

# ❓ Count frequency

```js id="k7l8m9"
const freq = {};

for (let item of arr) {
  freq[item] = (freq[item] || 0) + 1;
}
```

💀 VERY IMPORTANT

---

# 🔥 ARRAY vs OBJECT

| Feature   | Array   | Object |
| --------- | ------- | ------ |
| Ordered   | ✔       | ❌      |
| Indexed   | ✔       | ❌      |
| Key-value | limited | ✔      |
| Iteration | easy    | medium |

---

# 🔥 REAL INTERVIEW QUESTIONS

---

## ❓ Difference slice vs splice?

👉 slice:

* non-mutating

👉 splice:

* mutates original

---

## ❓ Difference find vs filter?

👉 find → first item
👉 filter → all items

---

## ❓ Why sort behaves weird?

👉 because default sort converts to string

---

# 🧠 GOLDEN INTERVIEW LINES

👉 “Objects are reference types storing key-value pairs.”

👉 “Arrays are specialized objects with ordered indexes.”

👉 “Many array methods mutate the original array, which is important to remember.”

---

# 🎯 FINAL CHECKLIST

Agar tum:

✔ object access
✔ keys/values/entries
✔ dynamic keys
✔ array methods
✔ slice vs splice
✔ find/filter
✔ some/every
✔ sort trap
✔ mutation awareness

samajh gaye →

👉 then you are **VERY STRONG in core JavaScript 💀🔥**

---
