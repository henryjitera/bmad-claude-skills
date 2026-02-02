---
title: Avoid Side Effects (part 2)
impact: CRITICAL
impactDescription: Prevents mutation of passed objects
tags: functions, side-effects, immutability
---

## Avoid Side Effects (part 2)

**Impact: CRITICAL (Prevents mutation of passed objects)**

In JavaScript, primitives are passed by value and objects/arrays are passed by reference. Be careful not to mutate objects passed as parameters, as this can cause bugs elsewhere.

**Incorrect (mutating input object):**

```javascript
const addItemToCart = (cart, item) => {
  cart.push({ item, date: Date.now() });
};
```

**Correct (returning new array):**

```javascript
const addItemToCart = (cart, item) => {
  return [...cart, { item, date: Date.now() }];
};
```

The immutable version creates a new array instead of modifying the input. The original cart remains unchanged, preventing side effects.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-side-effects-part-2)
