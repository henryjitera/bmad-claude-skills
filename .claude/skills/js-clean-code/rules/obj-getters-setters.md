---
title: Use getters and setters
impact: MEDIUM-HIGH
impactDescription: Provides better encapsulation and control
tags: objects, getters, setters, encapsulation
---

## Use getters and setters

**Impact: MEDIUM-HIGH (Provides better encapsulation and control)**

Using getters and setters to access data on objects could be better than simply looking for a property on an object. You can add validation, make getting properties easier, or encapsulate the internal representation.

**Incorrect (direct property access):**

```javascript
function makeBankAccount() {
  // ...

  return {
    balance: 0
    // ...
  };
}

const account = makeBankAccount();
account.balance = 100;
```

**Correct (using getters and setters):**

```javascript
function makeBankAccount() {
  // this one is private
  let balance = 0;

  // a "getter", made public via the returned object below
  function getBalance() {
    return balance;
  }

  // a "setter", made public via the returned object below
  function setBalance(amount) {
    // ... validate before updating the balance
    balance = amount;
  }

  return {
    // ...
    getBalance,
    setBalance
  };
}

const account = makeBankAccount();
account.setBalance(100);
```

Benefits include:
- You can add validation logic when setting a property
- Encapsulates the internal representation
- Easy to add logging and error handling
- Lazy loading object's properties

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#use-getters-and-setters)
