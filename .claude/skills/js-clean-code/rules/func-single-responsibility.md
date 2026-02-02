---
title: Functions should do one thing
impact: CRITICAL
impactDescription: Most important rule in software engineering
tags: functions, single-responsibility, design
---

## Functions should do one thing

**Impact: CRITICAL (Most important rule in software engineering)**

This is by far the most important rule in software engineering. When functions do more than one thing, they are harder to compose, test, and reason about.

**Incorrect (multiple responsibilities):**

```javascript
function emailClients(clients) {
  clients.forEach(client => {
    const clientRecord = database.lookup(client);
    if (clientRecord.isActive()) {
      email(client);
    }
  });
}
```

**Correct (single responsibility):**

```javascript
function emailActiveClients(clients) {
  clients
    .filter(isActiveClient)
    .forEach(email);
}

function isActiveClient(client) {
  const clientRecord = database.lookup(client);
  return clientRecord.isActive();
}
```

The improved version separates concerns: one function for filtering active clients, another for emailing. Each function does exactly one thing and does it well.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing)
