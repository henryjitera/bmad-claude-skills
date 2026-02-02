---
title: Don't ignore rejected promises
impact: HIGH
impactDescription: Ensures promise rejections are handled
tags: error-handling, promises, async
---

## Don't ignore rejected promises

**Impact: HIGH (Ensures promise rejections are handled)**

For the same reason you shouldn't ignore caught errors from try/catch, you shouldn't ignore rejected promises either.

**Incorrect (ignoring rejections):**

```javascript
getdata()
  .then(data => {
    functionThatMightThrow(data);
  })
  .catch(error => {
    console.log(error);
  });
```

**Correct (handling rejections properly):**

```javascript
getdata()
  .then(data => {
    functionThatMightThrow(data);
  })
  .catch(error => {
    // One option (more noisy than console.log):
    console.error(error);
    // Another option:
    notifyUserOfError(error);
    // Another option:
    reportErrorToService(error);
    // OR do all three!
  });
```

Always handle promise rejections properly with meaningful error handling strategies.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-ignore-rejected-promises)
