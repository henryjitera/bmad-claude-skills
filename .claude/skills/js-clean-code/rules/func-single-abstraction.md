---
title: Functions should only be one level of abstraction
impact: HIGH
impactDescription: Keeps functions focused and composable
tags: functions, abstraction, design
---

## Functions should only be one level of abstraction

**Impact: HIGH (Keeps functions focused and composable)**

When you have more than one level of abstraction, your function is usually doing too much. Splitting up functions leads to reusability and easier testing.

**Incorrect (multiple abstraction levels):**

```javascript
function parseBetterJSAlternative(code) {
  const REGEXES = [
    // ...
  ];

  const statements = code.split(" ");
  const tokens = [];
  REGEXES.forEach(REGEX => {
    statements.forEach(statement => {
      // ...
    });
  });

  const ast = [];
  tokens.forEach(token => {
    // lex...
  });

  ast.forEach(node => {
    // parse...
  });
}
```

**Correct (single abstraction level):**

```javascript
function parseBetterJSAlternative(code) {
  const tokens = tokenize(code);
  const syntaxTree = parse(tokens);
  syntaxTree.forEach(node => {
    // parse...
  });
}

function tokenize(code) {
  const REGEXES = [
    // ...
  ];

  const statements = code.split(" ");
  const tokens = [];
  REGEXES.forEach(REGEX => {
    statements.forEach(statement => {
      tokens.push(/* ... */);
    });
  });

  return tokens;
}

function parse(tokens) {
  const syntaxTree = [];
  tokens.forEach(token => {
    syntaxTree.push(/* ... */);
  });

  return syntaxTree;
}
```

Each function now operates at a single level of abstraction and has a clear, focused purpose.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#functions-should-only-be-one-level-of-abstraction)
