---
title: Open/Closed Principle (OCP)
impact: HIGH
impactDescription: Enables extension without modification
tags: solid, ocp, open-closed, design
---

## Open/Closed Principle (OCP)

**Impact: HIGH (Enables extension without modification)**

As stated by Bertrand Meyer, "software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification." This means you should be able to add new functionality without changing existing code.

**Incorrect (modifying existing code for new functionality):**

```javascript
class AjaxAdapter extends Adapter {
  constructor() {
    super();
    this.name = "ajaxAdapter";
  }
}

class NodeAdapter extends Adapter {
  constructor() {
    super();
    this.name = "nodeAdapter";
  }
}

class HttpRequester {
  constructor(adapter) {
    this.adapter = adapter;
  }

  fetch(url) {
    if (this.adapter.name === "ajaxAdapter") {
      return makeAjaxCall(url).then(response => {
        // transform response and return
      });
    } else if (this.adapter.name === "nodeAdapter") {
      return makeHttpCall(url).then(response => {
        // transform response and return
      });
    }
  }
}
```

**Correct (extending through polymorphism):**

```javascript
class AjaxAdapter extends Adapter {
  constructor() {
    super();
    this.name = "ajaxAdapter";
  }

  request(url) {
    // request and return promise
  }
}

class NodeAdapter extends Adapter {
  constructor() {
    super();
    this.name = "nodeAdapter";
  }

  request(url) {
    // request and return promise
  }
}

class HttpRequester {
  constructor(adapter) {
    this.adapter = adapter;
  }

  fetch(url) {
    return this.adapter.request(url).then(response => {
      // transform response and return
    });
  }
}
```

The improved version uses polymorphism, allowing new adapters to be added without modifying HttpRequester.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#openclosed-principle-ocp)
