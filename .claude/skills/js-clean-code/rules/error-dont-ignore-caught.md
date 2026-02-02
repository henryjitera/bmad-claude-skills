---
title: Don't ignore caught errors
impact: HIGH
impactDescription: Ensures errors are properly handled
tags: error-handling, try-catch, debugging
---

## Don't ignore caught errors

**Impact: HIGH (Ensures errors are properly handled)**

Doing nothing with a caught error doesn't give you the ability to ever fix or react to said error. Logging the error to the console isn't much better as often times it can get lost in a sea of things printed to the console. If you wrap any bit of code in a try/catch it means you think an error may occur there and therefore you should have a plan, or create a code path, for when it occurs.

**Incorrect (ignoring errors):**

```javascript
try {
  functionThatMightThrow();
} catch (error) {
  console.log(error);
}
```

**Correct (handling errors properly):**

```javascript
try {
  functionThatMightThrow();
} catch (error) {
  // One option (more noisy than console.log):
  console.error(error);
  // Another option:
  notifyUserOfError(error);
  // Another option:
  reportErrorToService(error);
  // OR do all three!
}
```

Proper error handling includes logging, notifying users, and/or reporting to error tracking services.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-ignore-caught-errors)
