---
title: Only comment things that have business logic complexity
impact: LOW-MEDIUM
impactDescription: Reduces noise and focuses on what matters
tags: comments, documentation, readability
---

## Only comment things that have business logic complexity

**Impact: LOW-MEDIUM (Reduces noise and focuses on what matters)**

Comments are an apology, not a requirement. Good code mostly documents itself. Only comment when the business logic is complex or when explaining why a non-obvious decision was made.

**Incorrect (unnecessary comments):**

```javascript
function hashIt(data) {
  // The hash
  let hash = 0;

  // Length of string
  const length = data.length;

  // Loop through every character in data
  for (let i = 0; i < length; i++) {
    // Get character code.
    const char = data.charCodeAt(i);
    // Make the hash
    hash = (hash << 5) - hash + char;
    // Convert to 32-bit integer
    hash &= hash;
  }
}
```

**Correct (only necessary comments):**

```javascript
function hashIt(data) {
  let hash = 0;
  const length = data.length;

  for (let i = 0; i < length; i++) {
    const char = data.charCodeAt(i);
    hash = (hash << 5) - hash + char;

    // Convert to 32-bit integer
    hash &= hash;
  }
}
```

The code itself explains what it does. Only the non-obvious bit-manipulation needs a comment.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#only-comment-things-that-have-business-logic-complexity)
