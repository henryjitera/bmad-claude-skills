---
title: Don't write to global functions
impact: HIGH
impactDescription: Prevents conflicts and unexpected behavior
tags: functions, globals, prototype
---

## Don't write to global functions

**Impact: HIGH (Prevents conflicts and unexpected behavior)**

Polluting globals is a bad practice in JavaScript because you could clash with another library and the user of your API would be none-the-wiser until they get an exception in production.

**Incorrect (extending Array.prototype):**

```javascript
Array.prototype.diff = function diff(comparisonArray) {
  const hash = new Set(comparisonArray);
  return this.filter(elem => !hash.has(elem));
};
```

**Correct (using ES6 class extension):**

```javascript
class SuperArray extends Array {
  diff(comparisonArray) {
    const hash = new Set(comparisonArray);
    return this.filter(elem => !hash.has(elem));
  }
}
```

By extending the built-in class instead of modifying its prototype, you avoid global namespace pollution and potential conflicts.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-write-to-global-functions)
