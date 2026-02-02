---
title: Single Responsibility Principle (SRP)
impact: HIGH
impactDescription: Makes classes easier to maintain and test
tags: solid, srp, single-responsibility, design
---

## Single Responsibility Principle (SRP)

**Impact: HIGH (Makes classes easier to maintain and test)**

As stated in Clean Code, "There should never be more than one reason for a class to change". It's tempting to jam-pack a class with a lot of functionality. The problem with this is that your class won't be conceptually cohesive and it will give it many reasons to change.

**Incorrect (multiple responsibilities):**

```javascript
class UserSettings {
  constructor(user) {
    this.user = user;
  }

  changeSettings(settings) {
    if (this.verifyCredentials()) {
      // ...
    }
  }

  verifyCredentials() {
    // ...
  }
}
```

**Correct (single responsibility):**

```javascript
class UserAuth {
  constructor(user) {
    this.user = user;
  }

  verifyCredentials() {
    // ...
  }
}

class UserSettings {
  constructor(user) {
    this.user = user;
    this.auth = new UserAuth(user);
  }

  changeSettings(settings) {
    if (this.auth.verifyCredentials()) {
      // ...
    }
  }
}
```

Now authentication and settings management are separate concerns, each with a single responsibility.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#single-responsibility-principle-srp)
