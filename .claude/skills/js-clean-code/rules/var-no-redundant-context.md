---
title: Don't add needless context
impact: MEDIUM
impactDescription: Keeps code concise without sacrificing clarity
tags: variables, naming, conciseness
---

## Don't add needless context

**Impact: MEDIUM (Keeps code concise without sacrificing clarity)**

If your class/object name tells you something, don't repeat that information in your variable names. The context is already provided by the container.

**Incorrect (redundant context):**

```javascript
const Car = {
  carMake: "Honda",
  carModel: "Accord",
  carColor: "Blue"
};

function paintCar(car, color) {
  car.carColor = color;
}
```

**Correct (context from object name):**

```javascript
const Car = {
  make: "Honda",
  model: "Accord",
  color: "Blue"
};

function paintCar(car, color) {
  car.color = color;
}
```

We already know it's a car from the object name, so prefixing properties with "car" is redundant.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#dont-add-needless-context)
