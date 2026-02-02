---
title: Use meaningful and pronounceable variable names
impact: HIGH
impactDescription: Makes code self-documenting and easier to understand
tags: variables, naming, readability
---

## Use meaningful and pronounceable variable names

**Impact: HIGH (Makes code self-documenting and easier to understand)**

Variable names should be meaningful and pronounceable. Avoid cryptic abbreviations that require mental decoding. We read code much more than we write it, so optimize for readability.

**Incorrect (cryptic abbreviations):**

```javascript
const yyyymmdstr = moment().format("YYYY/MM/DD");
```

**Correct (clear, pronounceable names):**

```javascript
const currentDate = moment().format("YYYY/MM/DD");
```

The correct version uses a name that clearly communicates intent and can be easily spoken in conversations about the code.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-meaningful-and-pronounceable-variable-names)
