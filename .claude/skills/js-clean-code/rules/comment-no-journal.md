---
title: Don't leave commented out code in your codebase
impact: LOW-MEDIUM
impactDescription: Reduces clutter and confusion
tags: comments, maintenance, version-control
---

## Don't leave commented out code in your codebase

**Impact: LOW-MEDIUM (Reduces clutter and confusion)**

Version control exists for a reason. Leave old code in your history. Commented-out code creates clutter and makes people wonder why it's there.

**Incorrect (leaving commented code):**

```javascript
doStuff();
// doOtherStuff();
// doSomeMoreStuff();
// doSoMuchStuff();
```

**Correct (clean code):**

```javascript
doStuff();
```

If you need old code, use version control (git) to retrieve it. Don't clutter your codebase with dead code.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-leave-commented-out-code-in-your-codebase)
