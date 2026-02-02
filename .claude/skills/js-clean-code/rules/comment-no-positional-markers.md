---
title: Don't use positional markers
impact: LOW
impactDescription: Reduces visual clutter
tags: comments, formatting, readability
---

## Don't use positional markers

**Impact: LOW (Reduces visual clutter)**

They usually just add noise. Let the functions and variable names along with the proper indentation and formatting give the visual structure to your code.

**Incorrect (using positional markers):**

```javascript
////////////////////////////////////////////////////////////////////////////////
// Scope Model Instantiation
////////////////////////////////////////////////////////////////////////////////
$scope.model = {
  menu: "foo",
  nav: "bar"
};

////////////////////////////////////////////////////////////////////////////////
// Action setup
////////////////////////////////////////////////////////////////////////////////
const actions = function() {
  // ...
};
```

**Correct (clean code without markers):**

```javascript
$scope.model = {
  menu: "foo",
  nav: "bar"
};

const actions = function() {
  // ...
};
```

Good code structure and naming make these separators unnecessary.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-have-journal-comments)
