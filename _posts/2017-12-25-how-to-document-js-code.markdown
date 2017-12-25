---
layout: post
title:  "How to document Javascript code"
date:   2017-12-25 22:26:40 +0100
categories: javascript, js, documentation
---
This article gives best-practices for documenting Javascript code with JSDoc:

## The Tags

* `@param` is **a tag**: This tag indicates that we'll be documenting a function's parameter.
* `{number}` is **a type**. It says that the input to this function is
  a JavaScript "number". It could also say `{string}`,
  `{Object}`, `{Date}`, or any other JavaScript built-in type. And if you
  defined a custom class, like `FooClass`, you can use it as a type too by
  saying `{FooClass}`.
* `input` is the name of the input variable. It matches what the code
  says right below it (`function addOne(input)`).
* `any number` is the description of the input.

On the third line, there's `@returns`. JavaScript returned values 
don't have names, so we just have a description of the value.

## Classes

**Document constructor parameters with the class, not the constructor method.**

Do:

```js
/**
 * A table object
 * @param {number} width
 * @param {number} height
 */
class Table {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
}
```

Don't:

```js
/** A table object */
class Table {
  /*
   * @param {number} width
   * @param {number} height
   */
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
}
```

## CommonJS modules
Do:

```
/**
 * A module for adding two values.
 * @module add-two-values
 */

/**
 * Add two values.
 * @alias module:add-two-values
 */
function add (a, b) {
  return a + b
}

module.exports = add
```

Don't:

```
/**
 * A module for adding two values.
 * @module add-two-values
 */

/**
 * Add two values.
 * @alias module:add-two-values
 */
function add (a, b) {
  return a + b
}

module.exports = add
```

## Promises

```
/**
 * Returns a promise for something.
 *
 * @returns {Promise}
 * @fulfil {string} - The data you wanted.
 * @reject {Error} - The error `name` property will be one of the following:
 *
 * - `NO_THANKS`: Computer doesn't want to.
 * - `TOO_MUCH`: Too much work, get some other app to do it.
 */
function getSomething () {}
```

## Todo lists

```
/**
 * @todo Write the documentation.
 * @todo Implement this function.
 */
function add () {}

/**
 * @todo Write the documentation.
 * @todo Implement this function.
 * @done this one is done
 * @done finished
 */
function subtract () {}

/**
 * @done this one is done
 * @done finished
 */
function multiply () {}
```

## Object params

```
/**
 * Makes a request to a secure web server.
 * @param options {object|string} - `options` can be an object or a string. If options is a string, it is automatically parsed with url.parse(). All options from `http.request()` are valid.
 * @param [options.host=localhost] {string} - A domain name or IP address of the server to issue the request to. Defaults to 'localhost'.
 * @param [options.family=4] {number} - IP address family to use when resolving host and hostname. Valid values are 4 or 6. When unspecified, both IP v4 and v6 will be used.
 * @param [options.path=/] {string} - Request path. Defaults to '/'. Should include query string if any. E.G. '/index.html?page=12'. An exception is thrown when the request path contains illegal characters. Currently, only spaces are rejected but that may change in the future.
 * @param [options.rejectUnauthorized=true] {boolean} - If true, the server certificate is verified against the list of supplied CAs. An 'error' event is emitted if verification fails. Verification happens at the connection level, before the HTTP request is sent.
 */
function request (options) {}
```


## List of documentation tools

* [documentation](https://github.com/documentationjs/documentation)
* [jsdoc-to-markdown](https://github.com/jsdoc2md/jsdoc-to-markdown)
* [dox](https://github.com/tj/dox)

## More best practices

* See more best practices at [Documentation help](https://github.com/documentationjs/documentation/blob/master/docs/RECIPES.md) and [jsdoc2md help](https://github.com/jsdoc2md/jsdoc-to-markdown/wiki).
* More essentials is found in the [documentation.js docs](https://github.com/documentationjs/documentation/blob/master/docs/GETTING_STARTED.md)
