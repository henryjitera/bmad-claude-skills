---
title: Remove dead code
impact: MEDIUM
impactDescription: Reduces maintenance burden and confusion
tags: functions, maintenance, cleanup
---

## Remove dead code

**Impact: MEDIUM (Reduces maintenance burden and confusion)**

Dead code is just as bad as duplicate code. There's no reason to keep it in your codebase. If it's not being called, get rid of it! It will still be safe in your version history if you ever need it again.

**Incorrect (keeping unused code):**

```javascript
function oldRequestModule(url) {
  // ...
}

function newRequestModule(url) {
  // ...
}

const req = newRequestModule;
inventoryTracker("apples", req, "www.inventory-awesome.io");
```

**Correct (removed unused code):**

```javascript
function newRequestModule(url) {
  // ...
}

const req = newRequestModule;
inventoryTracker("apples", req, "www.inventory-awesome.io");
```

Version control systems exist for a reason. Delete the old code and keep your codebase clean.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#remove-dead-code)
