---
title: Async/Await are even cleaner than Promises
impact: MEDIUM
impactDescription: Creates more readable async code
tags: async, async-await, promises, concurrency
---

## Async/Await are even cleaner than Promises

**Impact: MEDIUM (Creates more readable async code)**

Promises are a very clean alternative to callbacks, but ES2017/ES8 brings async and await which offer an even cleaner solution. All you need is a function that is prefixed in an async keyword, and then you can write your logic imperatively without a then chain of functions.

**Incorrect (promise chains):**

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

**Correct (using async/await):**

```javascript
import { get } from "request-promise";
import { writeFile } from "fs-extra";

async function getCleanCodeArticle() {
  try {
    const body = await get("https://en.wikipedia.org/wiki/Robert_Cecil_Martin");
    await writeFile("article.html", body);
    console.log("File written");
  } catch (err) {
    console.error(err);
  }
}

getCleanCodeArticle();
```

Async/await makes asynchronous code look and behave like synchronous code, improving readability.

Reference: [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript#asyncawait-are-even-cleaner-than-promises)
