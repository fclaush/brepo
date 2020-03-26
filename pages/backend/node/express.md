---
title: express
layout: page
---

## Setting Up Express Project

```
Franks-MacBook-Pro:Documents fclaush$ mkdir my-express-server
Franks-MacBook-Pro:Documents fclaush$ cd my-express-server
Franks-MacBook-Pro:my-express-server fclaush$ ls
Franks-MacBook-Pro:my-express-server fclaush$ touch server.js
Franks-MacBook-Pro:my-express-server fclaush$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (my-express-server)
version: (1.0.0)
description: First Test Server for EXPRESS
entry point: (server.js)
test command:
git repository:
keywords:
author: Francis Zeh
license: (ISC)
About to write to /Users/fclaush/Documents/my-express-server/package.json:

{
  "name": "my-express-server",
  "version": "1.0.0",
  "description": "First Test Server for EXPRESS",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  "author": "Francis Zeh",
  "license": "ISC"
}


Is this OK? (yes)
Franks-MacBook-Pro:my-express-server fclaush$ atom .
Franks-MacBook-Pro:my-express-server fclaush$ npm install express
```
