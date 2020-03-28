---
title: Backend Web Development - Node JS
layout: page
summary:
---

REPL Read Evaluation Print Loops

Node JS

https://nodejs.org/api/fs.html#fs_fs_copyfile_src_dest_flags_callback

node index.js

```
const fs = require('fs');

// destination.txt will be created or overwritten by default.
fs.copyFile('source.txt', 'destination.txt', (err) => {
  if (err) throw err;
  console.log('source.txt was copied to destination.txt');
});
```

NPM - Node Package Manager

https://www.npmjs.com/
