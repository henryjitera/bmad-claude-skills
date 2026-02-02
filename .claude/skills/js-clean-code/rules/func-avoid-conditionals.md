---
title: Avoid conditionals (use polymorphism)
impact: MEDIUM-HIGH
impactDescription: Creates more maintainable and extensible code
tags: functions, conditionals, polymorphism, oop
---

## Avoid conditionals (use polymorphism)

**Impact: MEDIUM-HIGH (Creates more maintainable and extensible code)**

This seems like an impossible task. Most people say, "how am I supposed to do anything without an if statement?" The answer is that you can use polymorphism to achieve the same task in many cases. When you have conditional logic, consider whether polymorphism might be a cleaner solution.

**Incorrect (conditional logic):**

```javascript
class Airplane {
  // ...
  getCruisingAltitude() {
    switch (this.type) {
      case "777":
        return this.getMaxAltitude() - this.getPassengerCount();
      case "Air Force One":
        return this.getMaxAltitude();
      case "Cessna":
        return this.getMaxAltitude() - this.getFuelExpenditure();
    }
  }
}
```

**Correct (polymorphism):**

```javascript
class Airplane {
  // ...
}

class Boeing777 extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude() - this.getPassengerCount();
  }
}

class AirForceOne extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude();
  }
}

class Cessna extends Airplane {
  // ...
  getCruisingAltitude() {
    return this.getMaxAltitude() - this.getFuelExpenditure();
  }
}
```

The polymorphic version is more maintainable and follows the Open/Closed Principle.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-conditionals)
