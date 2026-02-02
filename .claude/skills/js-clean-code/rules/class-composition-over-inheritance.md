---
title: Prefer composition over inheritance
impact: HIGH
impactDescription: Creates more flexible and maintainable designs
tags: classes, composition, inheritance, design-patterns
---

## Prefer composition over inheritance

**Impact: HIGH (Creates more flexible and maintainable designs)**

As stated famously in the Gang of Four's Design Patterns, you should prefer composition over inheritance where you can. There are lots of good reasons to use inheritance and lots of good reasons to use composition. The main point for this maxim is that if your mind instinctively goes for inheritance, try to think if composition could model your problem better.

When should you use inheritance?
1. Your inheritance represents an "is-a" relationship and not a "has-a" relationship (Human->Animal vs. User->UserDetails)
2. You can reuse code from the base classes
3. You want to make global changes to derived classes by changing a base class

**Incorrect (inheritance where composition is better):**

```javascript
class Employee {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }

  // ...
}

// Bad because Employees "have" tax data. EmployeeTaxData is not a type of Employee
class EmployeeTaxData extends Employee {
  constructor(ssn, salary) {
    super();
    this.ssn = ssn;
    this.salary = salary;
  }

  // ...
}
```

**Correct (using composition):**

```javascript
class EmployeeTaxData {
  constructor(ssn, salary) {
    this.ssn = ssn;
    this.salary = salary;
  }

  // ...
}

class Employee {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }

  setTaxData(ssn, salary) {
    this.taxData = new EmployeeTaxData(ssn, salary);
  }
  // ...
}
```

The composition version correctly models the "has-a" relationship between Employee and tax data.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#prefer-composition-over-inheritance)
