---
title: Function names should say what they do
impact: HIGH
impactDescription: Makes code self-documenting and intent clear
tags: functions, naming, readability
---

## Function names should say what they do

**Impact: HIGH (Makes code self-documenting and intent clear)**

Function names should clearly communicate what the function does. Avoid vague names that require reading the implementation to understand the purpose.

**Incorrect (vague naming):**

```javascript
function addToDate(date, month) {
  // ...
}

const date = new Date();

// It's hard to tell from the function name what is added
addToDate(date, 1);
```

**Correct (descriptive naming):**

```javascript
function addMonthToDate(month, date) {
  // ...
}

const date = new Date();
addMonthToDate(1, date);
```

The improved name makes it immediately clear that we're adding a month to a date, without needing to read the function body.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#function-names-should-say-what-they-do)
