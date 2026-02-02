---
title: Avoid type-checking
impact: MEDIUM
impactDescription: Enables cleaner, more flexible code
tags: functions, type-checking, polymorphism
---

## Avoid type-checking

**Impact: MEDIUM (Enables cleaner, more flexible code)**

JavaScript is untyped, which means your functions can take any type of argument. Sometimes you are bitten by this freedom and it becomes tempting to do type-checking in your functions. There are many ways to avoid having to do this. The first thing to consider is consistent APIs.

**Incorrect (type checking):**

```javascript
function travelToTexas(vehicle) {
  if (vehicle instanceof Bicycle) {
    vehicle.pedal(this.currentLocation, new Location("texas"));
  } else if (vehicle instanceof Car) {
    vehicle.drive(this.currentLocation, new Location("texas"));
  }
}
```

**Correct (polymorphism/duck typing):**

```javascript
function travelToTexas(vehicle) {
  vehicle.move(this.currentLocation, new Location("texas"));
}
```

If you're working with basic primitive values and you need type-checking, consider using TypeScript for compile-time type safety.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#avoid-type-checking-part-1)
