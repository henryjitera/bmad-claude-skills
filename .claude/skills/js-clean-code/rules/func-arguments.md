---
title: Function arguments (2 or fewer ideally)
impact: CRITICAL
impactDescription: Improves testability and reduces complexity
tags: functions, parameters, testing
---

## Function arguments (2 or fewer ideally)

**Impact: CRITICAL (Improves testability and reduces complexity)**

Limiting the amount of function parameters is incredibly important because it makes testing your function easier. Having more than three leads to a combinatorial explosion where you have to test tons of different cases with each separate argument.

**Incorrect (too many parameters):**

```javascript
function createMenu(title, body, buttonText, cancellable) {
  // ...
}

createMenu("Foo", "Bar", "Baz", true);
```

**Correct (use object destructuring):**

```javascript
function createMenu({ title, body, buttonText, cancellable }) {
  // ...
}

createMenu({
  title: "Foo",
  body: "Bar",
  buttonText: "Baz",
  cancellable: true
});
```

Using an object argument provides several benefits:
1. It's obvious what properties are being passed
2. You can use destructuring with default values
3. Linters can warn about unused properties
4. Order doesn't matter

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#function-arguments-2-or-fewer-ideally)
