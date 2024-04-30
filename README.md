# @devtea2026/cupiditate-dolorem-excepturi-impedit <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

ES Proposal spec-compliant shim for SuppressedError. Invoke its "shim" method to shim `SuppressedError` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment, and complies with the [proposed spec](https://tc39.es/proposal-explicit-resource-management/).

Most common usage:
```js
var assert = require('assert');
var SuppressedError = require('@devtea2026/cupiditate-dolorem-excepturi-impedit');

var suppressedError = new RangeError('hi!');
var cause = new EvalError('oops');
var error = new SuppressedError(cause, suppressedError, 'this is a suppressed error');

assert.equal(error.error, cause); // this is the cause of the suppression
assert.equal(error.suppressed, suppressedError);
assert.equal(error.message, 'this is a suppressed error');

SuppressedError.shim(); // will be a no-op if not needed

assert.ok(new globalThis.SuppressedError(null, '', {}) instanceof SuppressedError);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@devtea2026/cupiditate-dolorem-excepturi-impedit
[npm-version-svg]: https://versionbadg.es/devtea2026/cupiditate-dolorem-excepturi-impedit.svg
[deps-svg]: https://david-dm.org/devtea2026/cupiditate-dolorem-excepturi-impedit.svg
[deps-url]: https://david-dm.org/devtea2026/cupiditate-dolorem-excepturi-impedit
[dev-deps-svg]: https://david-dm.org/devtea2026/cupiditate-dolorem-excepturi-impedit/dev-status.svg
[dev-deps-url]: https://david-dm.org/devtea2026/cupiditate-dolorem-excepturi-impedit#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@devtea2026/cupiditate-dolorem-excepturi-impedit.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@devtea2026/cupiditate-dolorem-excepturi-impedit.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@devtea2026/cupiditate-dolorem-excepturi-impedit.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@devtea2026/cupiditate-dolorem-excepturi-impedit
[codecov-image]: https://codecov.io/gh/devtea2026/cupiditate-dolorem-excepturi-impedit/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/devtea2026/cupiditate-dolorem-excepturi-impedit/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/devtea2026/cupiditate-dolorem-excepturi-impedit
[actions-url]: https://github.com/devtea2026/cupiditate-dolorem-excepturi-impedit/actions
