---
title: Interface Segregation Principle (ISP)
impact: MEDIUM-HIGH
impactDescription: Prevents forcing unnecessary dependencies
tags: solid, isp, interface-segregation, design
---

## Interface Segregation Principle (ISP)

**Impact: MEDIUM-HIGH (Prevents forcing unnecessary dependencies)**

JavaScript doesn't have interfaces so this principle doesn't apply as strictly as others. However, it's important and relevant even with JavaScript's lack of type system. ISP states that "Clients should not be forced to depend upon interfaces that they do not use."

**Incorrect (forcing large configuration object):**

```javascript
class DOMTraverser {
  constructor(settings) {
    this.settings = settings;
    this.setup();
  }

  setup() {
    this.rootNode = this.settings.rootNode;
    this.settings.animationModule.setup();
  }

  traverse() {
    // ...
  }
}

const $ = new DOMTraverser({
  rootNode: document.getElementsByTagName("body"),
  animationModule() {} // Most of the time, we won't need to animate when traversing.
  // ...
});
```

**Correct (optional settings):**

```javascript
class DOMTraverser {
  constructor(settings) {
    this.settings = settings;
    this.options = settings.options;
    this.setup();
  }

  setup() {
    this.rootNode = this.settings.rootNode;
    this.setupOptions();
  }

  setupOptions() {
    if (this.options.animationModule) {
      // ...
    }
  }

  traverse() {
    // ...
  }
}

const $ = new DOMTraverser({
  rootNode: document.getElementsByTagName("body"),
  options: {
    animationModule() {}
  }
});
```

The improved version makes animationModule optional, not forcing clients to provide it.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#interface-segregation-principle-isp)
