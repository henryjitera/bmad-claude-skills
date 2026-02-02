---
title: Favor functional programming over imperative programming
impact: MEDIUM-HIGH
impactDescription: Creates cleaner, more declarative code
tags: functions, functional-programming, declarative
---

## Favor functional programming over imperative programming

**Impact: MEDIUM-HIGH (Creates cleaner, more declarative code)**

JavaScript isn't a functional language in the way that Haskell is, but it has a functional flavor to it. Functional programming is cleaner and easier to test. Favor this style of programming when you can.

**Incorrect (imperative loop):**

```javascript
const programmerOutput = [
  {
    name: "Uncle Bobby",
    linesOfCode: 500
  },
  {
    name: "Suzie Q",
    linesOfCode: 1500
  },
  {
    name: "Jimmy Gosling",
    linesOfCode: 150
  },
  {
    name: "Gracie Hopper",
    linesOfCode: 1000
  }
];

let totalOutput = 0;

for (let i = 0; i < programmerOutput.length; i++) {
  totalOutput += programmerOutput[i].linesOfCode;
}
```

**Correct (functional approach):**

```javascript
const programmerOutput = [
  {
    name: "Uncle Bobby",
    linesOfCode: 500
  },
  {
    name: "Suzie Q",
    linesOfCode: 1500
  },
  {
    name: "Jimmy Gosling",
    linesOfCode: 150
  },
  {
    name: "Gracie Hopper",
    linesOfCode: 1000
  }
];

const totalOutput = programmerOutput.reduce(
  (totalLines, output) => totalLines + output.linesOfCode,
  0
);
```

The functional version is more declarative and easier to understand at a glance.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#favor-functional-programming-over-imperative-programming)
