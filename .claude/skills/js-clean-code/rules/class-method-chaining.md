---
title: Use method chaining
impact: MEDIUM
impactDescription: Creates more fluent and expressive APIs
tags: classes, method-chaining, api-design
---

## Use method chaining

**Impact: MEDIUM (Creates more fluent and expressive APIs)**

Method chaining is a very useful pattern in JavaScript and you see it in many libraries. It allows your code to be expressive and less verbose. Return `this` from class methods to enable chaining.

**Incorrect (no method chaining):**

```javascript
class Car {
  constructor(make, model, color) {
    this.make = make;
    this.model = model;
    this.color = color;
  }

  setMake(make) {
    this.make = make;
  }

  setModel(model) {
    this.model = model;
  }

  setColor(color) {
    this.color = color;
  }

  save() {
    console.log(this.make, this.model, this.color);
  }
}

const car = new Car("Ford", "F-150", "red");
car.setColor("pink");
car.save();
```

**Correct (with method chaining):**

```javascript
class Car {
  constructor(make, model, color) {
    this.make = make;
    this.model = model;
    this.color = color;
  }

  setMake(make) {
    this.make = make;
    // NOTE: Returning this for chaining
    return this;
  }

  setModel(model) {
    this.model = model;
    // NOTE: Returning this for chaining
    return this;
  }

  setColor(color) {
    this.color = color;
    // NOTE: Returning this for chaining
    return this;
  }

  save() {
    console.log(this.make, this.model, this.color);
    // NOTE: Returning this for chaining
    return this;
  }
}

const car = new Car("Ford", "F-150", "red")
  .setColor("pink")
  .save();
```

Method chaining makes the code more fluent and readable.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-method-chaining)
