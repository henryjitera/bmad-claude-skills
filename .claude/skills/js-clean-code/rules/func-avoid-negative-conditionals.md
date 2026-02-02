---
title: Avoid negative conditionals
impact: MEDIUM
impactDescription: Reduces cognitive load when reading code
tags: functions, conditionals, readability
---

## Avoid negative conditionals

**Impact: MEDIUM (Reduces cognitive load when reading code)**

Negative conditionals require mental inversion to understand. Positive conditions are more natural to read and understand.

**Incorrect (negative conditional):**

```javascript
function isDOMNodeNotPresent(node) {
  // ...
}

if (!isDOMNodeNotPresent(node)) {
  // ...
}
```

**Correct (positive conditional):**

```javascript
function isDOMNodePresent(node) {
  // ...
}

if (isDOMNodePresent(node)) {
  // ...
}
```

The positive version eliminates the double negative (`!isDOMNodeNotPresent`), making the code much easier to understand.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-negative-conditionals)
