---
title: express
layout: page
---

## Setting Up Express Project

Starting and setting up the Express Server

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

Franks-MacBook-Pro:my-express-server fclaush$ pwd
/Users/fclaush/Documents/my-express-server
Franks-MacBook-Pro:my-express-server fclaush$ ls
node_modules            package-lock.json       package.json            server.js
Franks-MacBook-Pro:my-express-server fclaush$ open server.js

## server.js

```
const express = require("express");
const app = express();

app.listen(3000, function(){
  console.log("Server started on port 3000");
  });
```

## Start Node Server

Franks-MacBook-Pro:my-express-server fclaush$ node server.js
Server started on port 3000

```
const express = require("express");
const app = express();

app.get("/", function(request, response){
  console.log(request);
})

app.listen(3000, function(){
  console.log("Server started on port 3000");
  });
  ```

```
  const express = require("express");
const app = express();

app.get("/", function(req, res){
  res.send("<h1>hello world!</h1>");
});

app.listen(3000, function(){
  console.log("Server started on port 3000");
  });
  ```

  ## Nodemon
  Auto restart server

  https://nodemon.io/

  ```
  + nodemon@2.0.2
added 106 packages from 53 contributors in 7.541s
Franks-MacBook-Pro:my-express-server fclaush$ nodemon server.js
[nodemon] 2.0.2
[nodemon] to restart at any time, enter `rs`
[nodemon] watching dir(s): *.*
[nodemon] watching extensions: js,mjs,json
[nodemon] starting `node server.js`
Server started on port 3000
```
