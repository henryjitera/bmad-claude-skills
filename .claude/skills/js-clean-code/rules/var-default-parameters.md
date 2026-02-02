---
title: Use default parameters instead of short circuiting or conditionals
impact: MEDIUM
impactDescription: Makes default values explicit and cleaner
tags: variables, functions, parameters
---

## Use default parameters instead of short circuiting or conditionals

**Impact: MEDIUM (Makes default values explicit and cleaner)**

Use ES6 default parameters to specify default values clearly. This is more explicit and handles falsy values better than short-circuiting.

**Incorrect (short circuiting):**

```javascript
function createMicrobrewery(name) {
  const breweryName = name || "Hipster Brew Co.";
  // ...
}
```

**Correct (default parameters):**

```javascript
function createMicrobrewery(name = "Hipster Brew Co.") {
  // ...
}
```

Default parameters make the default value explicit in the function signature and handle `undefined` correctly without affecting other falsy values like `""` or `0`.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-default-arguments-instead-of-short-circuiting-or-conditionals)
