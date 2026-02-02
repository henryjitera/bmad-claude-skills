---
title: Use searchable names
impact: HIGH
impactDescription: Makes code easier to navigate and refactor
tags: variables, naming, maintainability
---

## Use searchable names

**Impact: HIGH (Makes code easier to navigate and refactor)**

We will read more code than we will ever write. It's important that the code we do write is readable and searchable. Avoid magic numbers and use named constants instead.

**Incorrect (magic numbers):**

```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```

**Correct (searchable named constants):**

```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```

Named constants are searchable, self-documenting, and can be refactored easily across the codebase.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-searchable-names)
