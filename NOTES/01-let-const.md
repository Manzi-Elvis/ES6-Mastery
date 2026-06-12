# Day 1 - ES6 Fundamentals

Today, I learned the foundation of modern JavaScript:

- let
- const
- Arrow functions
- Template literals
- Default parameters

---

# let

`let` is used for variables whose values can change.

```js
let age = 99;

age = 100;

console.log(age);
```

Output:

```txt
100
```

---

## Block Scope

Variables declared with `let` only exist inside their block.

```js
{
    let name = "Elvis";
}

console.log(name);
```

This produces:

```txt
ReferenceError: name is not defined
```

---

# const

`const` creates variables that cannot be reassigned.

```js
const country = "Rwanda";
```

Trying to change it:

```js
country = "Kenya";
```

Produces:

```txt
TypeError: Assignment to constant variable.
```

---

## Objects and Arrays with const

The contents can change.

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

# Arrow Functions

Normal function:

```js
function add(a, b) {
    return a + b;
}
```

Arrow function:

```js
const add = (a, b) => {
    return a + b;
};
```

---

## Implicit Return

```js
const square = num => num * num;

console.log(square(5));
```

Output:

```txt
25
```

---

## Returning Objects

Wrong:

```js
const createUser = () => {
    name: "Elvis";
};
```

Correct:

```js
const createUser = () => ({
    name: "Elvis"
});
```

---

# Template Literals

Old way:

```js
const name = "Elvis";

console.log("Hello " + name);
```

Modern way:

```js
const name = "Elvis";

console.log(`Hello ${name}`);
```

Output:

```txt
Hello Elvis
```

---

## Multiple Variables

```js
const name = "Elvis";
const age = 20;

console.log(`My name is ${name} and I am ${age} years old.`);
```

---

## Multi-line Strings

```js
console.log(`
JavaScript
ES6
Modern JS
`);
```

---

# Default Parameters

Without default values:

```js
function greet(name) {
    return `Hello ${name}`;
}

greet();
```

Output:

```txt
Hello undefined
```

---

With default values:

```js
function greet(name = "Guest") {
    return `Hello ${name}`;
}
```

Output:

```txt
Hello Guest
```

---

# Summary

| Concept | Purpose |
|---------|---------|
| let | Variables that change |
| const | Variables that shouldn't be reassigned |
| Arrow Functions | Shorter functions |
| Template Literals | Easier string formatting |
| Default Parameters | Default values for missing arguments |

---

# Key Takeaways

- Use `const` by default.
- Use `let` when values need to change.
- Prefer arrow functions.
- Use template literals instead of string concatenation.
- Use default parameters to avoid `undefined`.