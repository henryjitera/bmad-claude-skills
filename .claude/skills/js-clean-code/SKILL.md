---
name: js-clean-code
description: MUST be invoked when writing, reviewing, or refactoring any JavaScript/TypeScript code.
license: MIT
metadata:
  author: ryanmcdermott
  version: "1.0.0"
---

# JavaScript Clean Code

Comprehensive clean code principles for JavaScript applications based on Robert C. Martin's "Clean Code" adapted for JavaScript. Contains 40+ rules across 10 categories to guide writing readable, reusable, and refactorable code.

## When to Apply

Reference these guidelines when:
- Writing new JavaScript/TypeScript functions or modules
- Refactoring existing code for better readability
- Reviewing code for maintainability issues
- Designing class hierarchies and object structures
- Implementing error handling and asynchronous code
- Organizing code and choosing naming conventions

## Rule Categories by Priority

| Priority | Category | Impact | Prefix |
|----------|----------|--------|--------|
| 1 | Variables | HIGH | `var-` |
| 2 | Functions | CRITICAL | `func-` |
| 3 | Objects and Data Structures | MEDIUM-HIGH | `obj-` |
| 4 | Classes | MEDIUM-HIGH | `class-` |
| 5 | SOLID Principles | HIGH | `solid-` |
| 6 | Testing | CRITICAL | `test-` |
| 7 | Concurrency | MEDIUM | `async-` |
| 8 | Error Handling | HIGH | `error-` |
| 9 | Formatting | MEDIUM | `format-` |
| 10 | Comments | LOW-MEDIUM | `comment-` |

## Quick Reference

### 1. Variables (HIGH)

- `var-meaningful-names` - Use meaningful and pronounceable variable names
- `var-consistent-vocabulary` - Use the same vocabulary for the same type of variable
- `var-searchable-names` - Use searchable names
- `var-explanatory-variables` - Use explanatory variables
- `var-avoid-mental-mapping` - Avoid mental mapping
- `var-no-redundant-context` - Don't add needless context
- `var-default-parameters` - Use default parameters instead of short circuiting

### 2. Functions (CRITICAL)

- `func-arguments` - Function arguments (2 or fewer ideally)
- `func-single-responsibility` - Functions should do one thing
- `func-descriptive-names` - Function names should say what they do
- `func-single-abstraction` - Functions should only be one level of abstraction
- `func-no-duplicate` - Don't use flags as function parameters
- `func-avoid-side-effects` - Avoid Side Effects
- `func-dont-write-globals` - Don't write to global functions
- `func-favor-functional` - Favor functional programming over imperative
- `func-encapsulate-conditionals` - Encapsulate conditionals
- `func-avoid-negative-conditionals` - Avoid negative conditionals
- `func-avoid-conditionals` - Avoid conditionals (use polymorphism)
- `func-avoid-type-checking` - Avoid type-checking
- `func-remove-dead-code` - Remove dead code

### 3. Objects and Data Structures (MEDIUM-HIGH)

- `obj-getters-setters` - Use getters and setters
- `obj-private-members` - Make objects have private members

### 4. Classes (MEDIUM-HIGH)

- `class-es6-classes` - Prefer ES2015/ES6 classes over ES5 plain functions
- `class-method-chaining` - Use method chaining
- `class-composition-over-inheritance` - Prefer composition over inheritance

### 5. SOLID Principles (HIGH)

- `solid-single-responsibility` - Single Responsibility Principle (SRP)
- `solid-open-closed` - Open/Closed Principle (OCP)
- `solid-liskov-substitution` - Liskov Substitution Principle (LSP)
- `solid-interface-segregation` - Interface Segregation Principle (ISP)
- `solid-dependency-inversion` - Dependency Inversion Principle (DIP)

### 6. Testing (CRITICAL)

- `test-single-concept` - Single concept per test

### 7. Concurrency (MEDIUM)

- `async-promises-over-callbacks` - Prefer Promises to callbacks
- `async-await-over-promises` - Async/Await are even cleaner than Promises

### 8. Error Handling (HIGH)

- `error-dont-ignore-caught` - Don't ignore caught errors
- `error-dont-ignore-rejected` - Don't ignore rejected promises

### 9. Formatting (MEDIUM)

- `format-consistent-capitalization` - Use consistent capitalization
- `format-function-proximity` - Function callers and callees should be close

### 10. Comments (LOW-MEDIUM)

- `comment-only-business-logic` - Only comment things that have business logic complexity
- `comment-no-journal` - Don't leave commented out code in your codebase
- `comment-no-positional-markers` - Don't use positional markers

## How to Use

Read individual rule files for detailed explanations and code examples:

```
rules/var-meaningful-names.md
rules/func-single-responsibility.md
rules/_sections.md
```

Each rule file contains:
- Brief explanation of why it matters
- Incorrect code example with explanation
- Correct code example with explanation
- Additional context and references

## Full Compiled Document

For the complete guide with all rules expanded: `AGENTS.md`
