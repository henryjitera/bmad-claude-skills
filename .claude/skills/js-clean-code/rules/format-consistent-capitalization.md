---
title: Use consistent capitalization
impact: MEDIUM
impactDescription: Improves code readability and maintainability
tags: formatting, naming, consistency
---

## Use consistent capitalization

**Impact: MEDIUM (Improves code readability and maintainability)**

JavaScript is untyped, so capitalization tells you a lot about your variables, functions, etc. These rules are subjective, so your team can choose whatever they want. The point is, no matter what you all choose, just be consistent.

**Incorrect (inconsistent capitalization):**

```javascript
const DAYS_IN_WEEK = 7;
const daysInMonth = 30;

const songs = ["Back In Black", "Stairway to Heaven", "Hey Jude"];
const Artists = ["ACDC", "Led Zeppelin", "The Beatles"];

function eraseDatabase() {}
function restore_database() {}

class animal {}
class Alpaca {}
```

**Correct (consistent capitalization):**

```javascript
const DAYS_IN_WEEK = 7;
const DAYS_IN_MONTH = 30;

const SONGS = ["Back In Black", "Stairway to Heaven", "Hey Jude"];
const ARTISTS = ["ACDC", "Led Zeppelin", "The Beatles"];

function eraseDatabase() {}
function restoreDatabase() {}

class Animal {}
class Alpaca {}
```

Follow consistent conventions:
- UPPERCASE_WITH_UNDERSCORES for constants
- camelCase for variables and functions
- PascalCase for classes

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-consistent-capitalization)
