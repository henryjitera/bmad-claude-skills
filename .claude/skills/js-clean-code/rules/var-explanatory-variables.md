---
title: Use explanatory variables
impact: MEDIUM-HIGH
impactDescription: Breaks down complex expressions into understandable pieces
tags: variables, readability, clarity
---

## Use explanatory variables

**Impact: MEDIUM-HIGH (Breaks down complex expressions into understandable pieces)**

Decompose complex expressions using intermediate variables that explain what each part represents. This makes the code much easier to understand at a glance.

**Incorrect (complex nested expression):**

```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
saveCityZipCode(
  address.match(cityZipCodeRegex)[1],
  address.match(cityZipCodeRegex)[2]
);
```

**Correct (explanatory variables):**

```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
saveCityZipCode(city, zipCode);
```

The improved version extracts the match result into named variables, making it clear what data we're working with.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-explanatory-variables)
