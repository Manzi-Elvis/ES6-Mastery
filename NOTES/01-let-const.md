# let and const

Before ES6, JavaScript only had `var`.

```js
var age = 20;
```

ES6 introduced two new ways to declare variables:

- `let`
- `const`

These are safer and easier to work with.

---

# let

`let` is used for variables whose values may change later.

```js
let age = 20;

age = 21;

console.log(age);
```

Output:

```txt
21
```

---

# Reassigning Variables

```js
let score = 100;

score = 150;

console.log(score);
```

Output:

```txt
150
```

---

# Block Scope

Variables declared with `let` only exist inside their block.

```js
{
    let name = "Elvis";
}

console.log(name);
```

Output:

```txt
ReferenceError: name is not defined
```

---

## Example

```js
let age = 20;

if (age >= 18) {
    let message = "Adult";
}

console.log(message);
```

Output:

```txt
ReferenceError
```

Because `message` only exists inside the if block.

---

# const

`const` creates variables whose references cannot be reassigned.

```js
const country = "Rwanda";

country = "Kenya";
```

Output:

```txt
TypeError: Assignment to constant variable
```

---

# const Must Be Initialized

Wrong:

```js
const age;
```

Correct:

```js
const age = 20;
```

---

# Objects with const

Even though the variable itself cannot be reassigned, the contents of the object can change.

```js
const user = {
    name: "Elvis"
};

user.name = "John";

console.log(user);
```

Output:

```js
{
    name: "John"
}
```

---

# Arrays with const

```js
const colors = ["red", "blue"];

colors.push("green");

console.log(colors);
```

Output:

```js
["red", "blue", "green"]
```

---

# Reassigning Arrays

Wrong:

```js
const colors = ["red", "blue"];

colors = ["green"];
```

Output:

```txt
TypeError
```

---

# let vs const

```js
let age = 20;
age = 21;
```

Allowed.

---

```js
const PI = 3.14;
PI = 5;
```

Not allowed.

---

# Scope

Variables declared with `let` and `const` are block-scoped.

```js
{
    const x = 10;
}

console.log(x);
```

Output:

```txt
ReferenceError
```

---

# Best Practice

Use `const` by default.

Use `let` only when the value needs to change.

Avoid using `var`.

---

# Summary

| Keyword | Can Reassign? | Block Scoped? |
|----------|--------------|---------------|
| var | Yes | No |
| let | Yes | Yes |
| const | No | Yes |

---

# Golden Rule

Use:

```js
const
```

unless you know the value must change, then use:

```js
let
```