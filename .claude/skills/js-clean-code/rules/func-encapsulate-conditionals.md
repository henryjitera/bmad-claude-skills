---
title: Encapsulate conditionals
impact: MEDIUM
impactDescription: Makes complex conditions readable
tags: functions, conditionals, readability
---

## Encapsulate conditionals

**Impact: MEDIUM (Makes complex conditions readable)**

Complex conditionals should be extracted into well-named functions. This makes the intent clear and improves readability.

**Incorrect (inline complex condition):**

```javascript
if (fsm.state === "fetching" && isEmpty(listNode)) {
  // ...
}
```

**Correct (encapsulated condition):**

```javascript
function shouldShowSpinner(fsm, listNode) {
  return fsm.state === "fetching" && isEmpty(listNode);
}

if (shouldShowSpinner(fsmInstance, listNodeInstance)) {
  // ...
}
```

The function name `shouldShowSpinner` clearly communicates the intent of the condition.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#encapsulate-conditionals)
