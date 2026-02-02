---
title: Avoid Side Effects (part 1)
impact: CRITICAL
impactDescription: Prevents unintended state mutations
tags: functions, side-effects, immutability
---

## Avoid Side Effects (part 1)

**Impact: CRITICAL (Prevents unintended state mutations)**

A function produces a side effect if it does anything other than take a value in and return another value or values. Side effects can be writing to a file, modifying a global variable, or accidentally wiring all your money to a stranger.

**Incorrect (modifying shared state):**

```javascript
// Global variable referenced by following function.
let name = "Ryan McDermott";

function splitIntoFirstAndLastName() {
  name = name.split(" ");
}

splitIntoFirstAndLastName();

console.log(name); // ['Ryan', 'McDermott'];
```

**Correct (pure function):**

```javascript
function splitIntoFirstAndLastName(name) {
  return name.split(" ");
}

const name = "Ryan McDermott";
const newName = splitIntoFirstAndLastName(name);

console.log(name); // 'Ryan McDermott';
console.log(newName); // ['Ryan', 'McDermott'];
```

The pure function version takes input and returns output without modifying external state, making it predictable and testable.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-1)
