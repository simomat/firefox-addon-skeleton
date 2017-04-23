# firefox-addon-skeleton

A skeleton for Firefox add-on development. Usable for developing add-ons based on [WebExtensions](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) API.

[![devDependency Status](https://david-dm.org/simomat/firefox-addon-skeleton.svg)](https://david-dm.org/simomat/firefox-addon-skeleton#info=devDependencies)

It provides
 * package structure, `manifest.json` template
 * ability to write JavaScript in modules (ES6), which are bundled on build
 * running JavaScript tests
 * easy build, run, pack, sign through `npm run`
 * dependencies for doing all that

### How to use it

All you need is node and npm. Following npm scripts are defined:

```bash
$ npm run build   # bundles code and resources to ./dist
$ npm run clean   # perfomrs cleanup of ./dist and built artefacts
$ npm run test    # executes JavasSript tests
$ npm run start   # runs Firefox with own profile and the add-on installed (needs ./dist to be built)
$ npm run lint    # checks integrity of the add-on (needs ./dist to be built)
$ npm run pack    # packs the add-on as a .zip into ./web-ext-artifacts
$ npm run sign    # performs signation, builds .xpi into ./web-ext-artifacts on success
```

Note: for `npm sign`, WEB_EXT_API_KEY and WEB_EXT_API_SECRET environment variables need to be set. See [web-ext](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/web-ext_command_reference#web-ext_sign) docs.
 
 
### Tech base

 * [grunt](https://github.com/gruntjs/grunt) as build system
 * [web-ext](https://github.com/mozilla/web-ext) for all add-on relate stuff
 * [mocha](https://github.com/mochajs/mocha) as test runner
 * [rollup](https://github.com/rollup/rollup) to bundle ES6 modules
 * [babel](https://github.com/babel/babel) to run tests on ES6 modules


#### Not yet included
Some features an add-on may also have but which are not included in the skeleton yet:
 
 * internationalization
 * devtools page
 * page action
 * sidebar action
 * web accessible resources
