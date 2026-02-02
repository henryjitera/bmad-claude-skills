---
title: Don't use flags as function parameters
impact: HIGH
impactDescription: Signals function does more than one thing
tags: functions, parameters, single-responsibility
---

## Don't use flags as function parameters

**Impact: HIGH (Signals function does more than one thing)**

A flag immediately tells you that this function does more than one thing. Functions should do one thing. Split your functions if they are following different code paths based on a boolean.

**Incorrect (flag parameter):**

```javascript
function createFile(name, temp) {
  if (temp) {
    fs.create(`./temp/${name}`);
  } else {
    fs.create(name);
  }
}
```

**Correct (separate functions):**

```javascript
function createFile(name) {
  fs.create(name);
}

function createTempFile(name) {
  createFile(`./temp/${name}`);
}
```

Now each function has a single, clear purpose, and the caller's intent is explicit.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-use-flags-as-function-parameters)
