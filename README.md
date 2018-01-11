Another React Redux Electron Starter Kit
================================

This starter kit is an integration of Dave Zuko's amazing v3.0.1 [React Redux Starter Kit](https://github.com/davezuko/react-redux-starter-kit/tree/new-project-v2) but with upgraded dependencies and [Electron](http://electron.atom.io/) to get up and running in no time.

[![Build Status](https://travis-ci.org/kr1ck/another-react-redux-electron-starter-kit.svg?branch=master)](https://travis-ci.org/kr1ck/another-react-redux-electron-starter-kit?branch=master) [![dependencies](https://david-dm.org/kr1ck/another-react-redux-electron-starter-kit.svg)](https://david-dm.org/kr1ck/another-react-redux-electron-starter-kit) [![devDependency Status](https://david-dm.org/kr1ck/another-react-redux-electron-starter-kit/dev-status.svg)](https://david-dm.org/kr1ck/another-react-redux-electron-starter-kit#info=devDependencies) [![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com/)



Requirements
------------

* node `^6.11.4`
* npm `^3.0.0`

Features
--------

* [React](https://github.com/facebook/react) (`^16.2.0`)
* [Redux](https://github.com/rackt/redux) (`^3.6.0`)
  * react-redux (`^5.0.4`)
* [react-router](https://github.com/rackt/react-router) (`^2.0.0`)
* [react-router-redux](https://github.com/rackt/react-router-redux) (`^4.0.8`)
* [Webpack](https://github.com/webpack/webpack) (`^3.10.0`)
  * Bundle splitting and CSS extraction
  * Sass w/ CSS modules, autoprefixer, and minification
* [Karma](https://github.com/karma-runner/karma) (`^2.0.0`)
  * Mocha w/ chai, and chai-as-promised, and [chai-enzyme](https://github.com/producthunt/chai-enzyme) (`^1.0.0-beta.0`)
  * PhantomJS
* [Babel](https://github.com/babel/babel) (`^6.26.0`)
  * [redbox-react](https://github.com/KeywordBrain/redbox-react) (`^1.3.6`) visible error reporting for React components
  * [babel-plugin-transform-runtime](https://www.npmjs.com/package/babel-plugin-transform-runtime) (`^6.15.0`) so transforms aren't inlined
* [ESLint](http://eslint.org) (`^4.15.0`)
  * Uses [Standard Style](https://github.com/feross/standard) by default, but you're welcome to change this.

Getting Started
---------------

Just clone the repo and install the necessary node modules:

```shell
$ git clone https://github.com/kr1ck/another-react-redux-electron-starter-kit.git
$ cd another-react-redux-electron-starter-kit
$ yarn install                   # Install Node modules listed in ./package.json (may take a while the first time)
$ yarn start                     # Compile and launch the redux project
$ yarn start-app                 # Compile and launch electron app hot
```

Usage
-----

|`yarn .. OR npm run .. `|Description|
|---|---|
|`start`|Starts up server to serve your app at `localhost:3000`. HMR will be enabled in development.|
|`start-app`| Starts up an Electron instance pointing to `localhost:3000`. HMR will be enabled in development.|
|`test`|Runs unit tests with Karma.|
|`test:watch`|Runs test in watch mode to re-run tests when changed.|
|`lint`|Lint all `.js` files.|
|`lint:fix`|Lint and fix all `.js` files. [Read more on this](http://eslint.org/docs/user-guide/command-line-interface.html#fix).|
|`compile:dev` |Compiles code to app/dist with `NODE_ENV` as "development".|
|`compile:prod` |Compiles code to app/dist with `NODE_ENV` as "production".|
|`compile-prepare` |Prepares app folder with its package.json and node_modules.|
|`compile` |Compiles app's web code (react and redux).|
|`compile-electron` |Compiles app's electron code (from /electron).|
|`dist` |Builds app for distribution on /release.|
|`dist:linux` |Builds a linux app.|
|`dist:mac` |Builds a mac app.|
|`dist:win32` |Builds a win 32 app.|


Structure
---------


```
.
├── app                      # Dist files for the electron packaging
├── build                    # All build-related configuration
│   └── webpack              # Environment-specific configuration files for webpack
├── dist                     # Packaged apps will make their way here
├── electron                 # Electron code (ipc coming soon)
├── public                   # Static public assets (not imported anywhere in source code)
├── server                   # Express application that provides webpack middleware
│   └── main.js              # Server application entry point
├── src                      # Application source code
│   ├── index.html           # Main HTML page container for app
│   ├── main.js              # Application bootstrap and rendering
│   ├── normalize.js         # Browser normalization and polyfills
│   ├── components           # Global Reusable Components
│   ├── containers           # Global Reusable Container Components
│   ├── layouts              # Components that dictate major page structure
│   │   └── PageLayout       # Global application layout in which to render routes
│   ├── routes               # Main route definitions and async split points
│   │   ├── index.js         # Bootstrap main application routes with store
│   │   ├── Home             # Fractal route
│   │   │   ├── index.js     # Route definitions and async split points
│   │   │   ├── assets       # Assets required to render components
│   │   │   ├── components   # Presentational React Components
│   │   │   └── routes **    # Fractal sub-routes (** optional)
│   │   └── Counter          # Fractal route
│   │       ├── index.js     # Counter route definition
│   │       ├── container    # Connect components to actions and store
│   │       ├── modules      # Collections of reducers/constants/actions
│   │       └── routes **    # Fractal sub-routes (** optional)
│   ├── store                # Redux-specific pieces
│   │   ├── createStore.js   # Create and instrument redux store
│   │   └── reducers.js      # Reducer registry and injection
│   └── styles               # Application-wide styles (generally settings)
└── tests                    # Unit tests
```


Tests
---------
Tests are broken
