---
title: Use the same vocabulary for the same type of variable
impact: HIGH
impactDescription: Reduces cognitive load and maintains consistency
tags: variables, naming, consistency
---

## Use the same vocabulary for the same type of variable

**Impact: HIGH (Reduces cognitive load and maintains consistency)**

Use consistent terminology across your codebase for the same concepts. Don't use different words (getUserInfo, getClientData, getCustomerRecord) when you're referring to the same entity type.

**Incorrect (inconsistent vocabulary):**

```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```

**Correct (consistent vocabulary):**

```javascript
getUser();
```

Pick one word for one abstract concept and stick with it throughout your codebase.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-the-same-vocabulary-for-the-same-type-of-variable)
