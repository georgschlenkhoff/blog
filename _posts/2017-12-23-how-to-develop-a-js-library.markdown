---
layout: post
title:  "How to devleop a Javascript library"
date:   2017-12-23 15:26:40 +0100
categories: javascript, js
---
This article explains how to develop a Javascript library.

* Npm init
* Structure the package

```
  |package.json
  |lib
    |--index.js
    |--utils.js
  |test
    |--index.test.js
    |--utils.test.js
  |.tern-project
  |.gitignore
```

* Bootstrap `.gitignore`

```
node_modules/
coverage/
package-lock.json
downloads/
.nyc_output/
config.json
```

* Bootstrap `.tern-project`

```
{
  "libs": [
    "browser",
    "jquery"
  ],
  "plugins": {
    "requirejs": {
      "baseURL": "./",
      "paths": {}
    }
  }
}
```

* Bootstrap `.package.json`


```
{
  "name": "somename",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "nyc --reporter=text --reporter=html mocha --watch --recursive --timeout 5000 test/**/*.test.js"
  },
  "author": "Georg Schlenkhoff",
  "license": "ISC",
  "dependencies": {
  },
  "devDependencies": {
    "chai": "^4.1.2",
    "mocha": "^4.0.1",
    "nyc": "^11.4.1",
    "sinon": "^4.1.3"
  }
}
```

* Write the index.js as if new functions work
* Write integration test in index.js
* Scaffold functions with signatures
* Write unit tests for functions

====Iterate====

* Implement one function after the other
* Write JSDOC (:JsDoc in vim) for function

====Iterate====