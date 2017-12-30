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
  |index.js
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
    "chai",
    "ecmascript"
  ],
  "plugins": {
    "requirejs": {
      "baseURL": "./",
      "paths": {}
    },
    "node": {}
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
    "test": "nyc --reporter=text --reporter=html mocha --watch --recursive --timeout 5000 test/**/*.test.js",
    "docs": "node ./node_modules/documentation/bin/documentation.js build ./src/** -f html -o ./docs && node ./node_modules/documentation/bin/documentation.js readme ./src/** --section=API"
  },
  "author": "Georg Schlenkhoff",
  "license": "ISC",
  "dependencies": {
  },
  "devDependencies": {
    "babel-cli": "^6.26.0",
    "babel-eslint": "^8.1.2",
    "babel-minify": "^0.2.0",
    "babel-preset-env": "^1.6.1",
    "babel-preset-flow": "^6.23.0",
    "babel-preset-minify": "^0.2.0",
    "chai": "^4.1.2",
    "eslint": "^4.14.0",
    "eslint-plugin-flowtype": "^2.40.1",
    "flow-bin": "^0.61.0",
    "mocha": "^4.0.1",
    "documentation": "^5.3.5",
    "nyc": "^11.4.1",
    "sinon": "^4.1.3"
  }
}
```

* Bootstrap README.md

```
![logo](https://raw.githubusercontent.com/georgschlenkhoff/project/master/assets/logo.png)

Description

## Features

## Demo

![demo](https://raw.githubusercontent.com/georgschlenkhoff/project/master/assets/demo.png)

## Installation

## Usage

## API

## Contributors

* [georgschlenkhoff](https://github.com/georgschlenkhoff)
```

* Bootstrap . eslintrc.json

```
{
    "parser": "babel-eslint",
    "plugins": [
        "flowtype"
    ],
    "env": {
        "es6": true,
        "node": true
    },
    "extends": [
      "eslint:recommended",
      "plugin:flowtype/recommended"
    ],
    "rules": {
        "indent": [
            "error",
            2
        ],
        "linebreak-style": [
            "error",
            "unix"
        ],
        "quotes": [
            "error",
            "single"
        ],
        "semi": [
            "error",
            "never"
        ],
        "no-console": "off",
        "valid-jsdoc":
        [
          "error", { "prefer":
            { "arg": "param", "argument": "param", "class": "constructor", "return": "returns" }
          }
        ]
    }
}
```

* Bootstrap .babelrc

```
{
  "presets": ["flow"],
  "env": {}
}
```

* Start Babel cli with `npx babel

// TODO: bootstrap travis and babel
* Bootstrap Travis
* Initalise flow with `flow init` in `src` directory
* Start flow with `npx flow status`

* Amend README.md, describing capabilities and usage
* Write the index.js as if new functions work
* Write integration test in index.js
* Scaffold functions with signatures
* Write JsDoc comments, with help [:JsDoc](https://github.com/heavenshell/vim-jsdoc) in vim
* Build documentation with `npm run docs`
* Deploy `docs` folder to [GitHub Pages](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/)
* Write unit tests for functions

====Iterate====

* Implement one function after the other

====Iterate====
