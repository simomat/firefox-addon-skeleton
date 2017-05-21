# firefox-addon-skeleton

A skeleton for developing Firefox add-ons based on [WebExtensions](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) API.

[![devDependency Status](https://david-dm.org/simomat/firefox-addon-skeleton/dev-status.svg)](https://david-dm.org/simomat/firefox-addon-skeleton?type=dev)

It provides
 * package structure, `manifest.json` template
 * ability to write JavaScript in ES6 modules, which are bundled on build
 * running JavaScript tests
 * easy build, run, pack, sign through `npm run`
 * dependencies for doing all that

### How to use it

All you need is node and npm. Following npm scripts are defined:

```bash
$ npm run build   # bundles code and resources to ./dist
$ npm run clean   # performs cleanup of ./dist and built artifacts
$ npm run test    # executes JavasScript tests
$ npm run start   # runs Firefox with own profile and the add-on installed (needs ./dist to be built)
$ npm run lint    # checks integrity of the add-on (needs ./dist to be built)
$ npm run pack    # packs the add-on as a .zip into ./web-ext-artifacts
$ npm run sign    # performs signing, builds .xpi into ./web-ext-artifacts on success
```

Note: for `npm run sign`, WEB_EXT_API_KEY and WEB_EXT_API_SECRET environment variables need to be set. See [web-ext](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/web-ext_command_reference#web-ext_sign) docs.
 
 
### Tech base

 * [web-ext](https://github.com/mozilla/web-ext) for all add-on relate stuff
 * [gulp](https://github.com/gulpjs/gulp) as build system
 * [rollup](https://github.com/rollup/rollup) to bundle ES6 modules
 * [mocha](https://github.com/mochajs/mocha) as test runner
 * [babel](https://github.com/babel/babel) to run tests on ES6 modules

### Just want to have a taste?

Give it a try and see how WebExtensions integrate:
```bash
$ npm link
$ npm run build
$ npm run start
```

#### Not yet included
Some features of WebExtensions are not covered yet:
 
 * internationalization
 * devtools page
 * page action
 * sidebar action
 * web accessible resources
