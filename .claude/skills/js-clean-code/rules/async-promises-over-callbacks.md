---
title: Prefer Promises to callbacks
impact: MEDIUM
impactDescription: Eliminates callback hell and improves readability
tags: async, promises, callbacks, concurrency
---

## Prefer Promises to callbacks

**Impact: MEDIUM (Eliminates callback hell and improves readability)**

Callbacks aren't clean, and they cause excessive amounts of nesting. With ES2015/ES6, Promises are a built-in global type. Use them!

**Incorrect (callback hell):**

```javascript
import { get } from "request";
import { writeFile } from "fs";

get(
  "https://en.wikipedia.org/wiki/Robert_Cecil_Martin",
  (requestErr, response, body) => {
    if (requestErr) {
      console.error(requestErr);
    } else {
      writeFile("article.html", body, writeErr => {
        if (writeErr) {
          console.error(writeErr);
        } else {
          console.log("File written");
        }
      });
    }
  }
);
```

**Correct (using Promises):**

```javascript
import { get } from "request-promise";
import { writeFile } from "fs-extra";

get("https://en.wikipedia.org/wiki/Robert_Cecil_Martin")
  .then(body => {
    return writeFile("article.html", body);
  })
  .then(() => {
    console.log("File written");
  })
  .catch(err => {
    console.error(err);
  });
```

Promises provide a cleaner way to handle asynchronous operations with better error handling.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#prefer-promises-to-callbacks)
