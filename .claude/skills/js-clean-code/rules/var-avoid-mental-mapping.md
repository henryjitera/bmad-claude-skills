---
title: Avoid mental mapping
impact: MEDIUM-HIGH
impactDescription: Eliminates need to translate variable names in your head
tags: variables, naming, clarity
---

## Avoid mental mapping

**Impact: MEDIUM-HIGH (Eliminates need to translate variable names in your head)**

Explicit is better than implicit. Don't force readers to mentally translate what a variable represents. Single-letter variables are only acceptable in small loop contexts.

**Incorrect (requires mental mapping):**

```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(l => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  // Wait, what is `l` for again?
  dispatch(l);
});
```

**Correct (explicit naming):**

```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(location => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  dispatch(location);
});
```

The explicit name `location` makes it immediately clear what we're working with, even many lines later.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-mental-mapping)
