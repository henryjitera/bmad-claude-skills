---
title: Single concept per test
impact: CRITICAL
impactDescription: Makes tests easier to understand and maintain
tags: testing, test-design, maintainability
---

## Single concept per test

**Impact: CRITICAL (Makes tests easier to understand and maintain)**

Testing is more important than shipping. If you have no tests or an inadequate amount, then every time you ship code you won't be sure that you didn't break anything. Tests should be focused on a single concept to make failures easy to diagnose.

**Incorrect (multiple concepts in one test):**

```javascript
import assert from "assert";

describe("MomentJS", () => {
  it("handles date boundaries", () => {
    let date;

    date = new MomentJS("1/1/2015");
    date.addDays(30);
    assert.equal("1/31/2015", date);

    date = new MomentJS("2/1/2016");
    date.addDays(28);
    assert.equal("02/29/2016", date);

    date = new MomentJS("2/1/2015");
    date.addDays(28);
    assert.equal("03/01/2015", date);
  });
});
```

**Correct (one concept per test):**

```javascript
import assert from "assert";

describe("MomentJS", () => {
  it("handles 30-day months", () => {
    const date = new MomentJS("1/1/2015");
    date.addDays(30);
    assert.equal("1/31/2015", date);
  });

  it("handles leap year", () => {
    const date = new MomentJS("2/1/2016");
    date.addDays(28);
    assert.equal("02/29/2016", date);
  });

  it("handles non-leap year", () => {
    const date = new MomentJS("2/1/2015");
    date.addDays(28);
    assert.equal("03/01/2015", date);
  });
});
```

Each test now focuses on a single scenario, making it clear what failed when a test breaks.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#single-concept-per-test)
