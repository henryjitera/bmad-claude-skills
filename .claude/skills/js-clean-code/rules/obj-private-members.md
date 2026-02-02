---
title: Make objects have private members
impact: MEDIUM-HIGH
impactDescription: Enforces encapsulation and data hiding
tags: objects, private, encapsulation, closures
---

## Make objects have private members

**Impact: MEDIUM-HIGH (Enforces encapsulation and data hiding)**

This can be accomplished through closures (for ES5 and below) or using private fields (ES2020+). True privacy ensures internal implementation details cannot be accessed or modified from outside.

**Incorrect (public members):**

```javascript
const Employee = function(name) {
  this.name = name;
};

Employee.prototype.getName = function getName() {
  return this.name;
};

const employee = new Employee("John Doe");
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name;
console.log(`Employee name: ${employee.getName()}`); // Employee name: undefined
```

**Correct (private members with closures):**

```javascript
function makeEmployee(name) {
  return {
    getName() {
      return name;
    }
  };
}

const employee = makeEmployee("John Doe");
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
delete employee.name;
console.log(`Employee name: ${employee.getName()}`); // Employee name: John Doe
```

The closure-based version keeps `name` truly private and prevents external manipulation.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#make-objects-have-private-members)
