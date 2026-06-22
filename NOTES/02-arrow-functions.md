# Arrow Functions

Arrow functions are a shorter and cleaner way to write functions introduced in ES6.

Before ES6, functions were written like this:

```js
function greet() {
    return "Hello";
}
```

With ES6:

```js
const greet = () => {
    return "Hello";
};
```

Both do the same thing.

---

# Basic Syntax

```js
const functionName = () => {
    // code
};
```

Example:

```js
const sayHello = () => {
    return "Hello";
};

console.log(sayHello());
```

Output:

```txt
Hello
```

---

# One Parameter

If there is only one parameter, parentheses are optional.

```js
const square = num => {
    return num * num;
};

console.log(square(5));
```

Output:

```txt
25
```

---

# Multiple Parameters

When there are two or more parameters, parentheses are required.

```js
const add = (a, b) => {
    return a + b;
};

console.log(add(3, 4));
```

Output:

```txt
7
```

---

# Implicit Return

If the function has only one statement, you can omit `return` and curly braces.

Instead of:

```js
const double = num => {
    return num * 2;
};
```

You can write:

```js
const double = num => num * 2;
```

Output:

```txt
double(4) → 8
```

---

# No Parameters

Use empty parentheses.

```js
const greet = () => "Hello";

console.log(greet());
```

Output:

```txt
Hello
```

---

# Returning Objects

Wrong:

```js
const createUser = () => {
    name: "Elvis";
};
```

This returns `undefined`.

Correct:

```js
const createUser = () => ({
    name: "Elvis"
});

console.log(createUser());
```

Output:

```js
{
    name: "Elvis"
}
```

---

# Arrow Functions with Arrays

```js
const numbers = [1, 2, 3];

numbers.forEach(num => {
    console.log(num);
});
```

Output:

```txt
1
2
3
```

---

# Arrow Functions as Variables

```js
const multiply = (a, b) => a * b;

console.log(multiply(4, 5));
```

Output:

```txt
20
```

---

# Arrow Functions and this

Normal functions have their own `this`.

Arrow functions do not create their own `this`; they inherit it from their surrounding scope.

Example:

```js
const person = {
    name: "Elvis",

    greet() {
        console.log(this.name);
    }
};

person.greet();
```

Output:

```txt
Elvis
```

---

# When to Use Arrow Functions

Good for:

- Small functions
- Callback functions
- Array methods
- Functional programming

Examples:

```js
array.map()
array.filter()
array.find()
array.reduce()
forEach()
```

---

# When Not to Use Arrow Functions

Avoid using arrow functions as object methods when you need `this`.

Bad:

```js
const person = {
    name: "Elvis",

    greet: () => {
        console.log(this.name);
    }
};
```

Output:

```txt
undefined
```

---

# Summary

| Situation | Syntax |
|------------|--------|
| No parameters | `() => {}` |
| One parameter | `num => {}` |
| Multiple parameters | `(a, b) => {}` |
| Implicit return | `num => num * 2` |
| Return object | `() => ({ name: "Elvis" })` |

---

# Golden Rules

- Use arrow functions for short functions.
- Use implicit return when possible.
- Wrap returned objects in parentheses.
- Be careful with `this`.