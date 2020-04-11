<img src="https://raw.githubusercontent.com/MobileFirstLLC/extension-cli/master/guide/assets/images/favicon.png" width="64" alt="Extension CLI">  

# Extension CLI

[![npm](https://img.shields.io/npm/v/extension-cli)](https://www.npmjs.com/package/extension-cli)
[![travis](https://img.shields.io/travis/mobilefirstllc/extension-cli)](https://travis-ci.org/MobileFirstLLC/extension-cli)
[![david](https://img.shields.io/david/mobilefirstllc/extension-cli)](https://david-dm.org/mobilefirstllc/extension-cli)
[![Maintainability](https://api.codeclimate.com/v1/badges/abbf1b25f926d75bb9df/maintainability)](https://codeclimate.com/github/MobileFirstLLC/extension-cli/maintainability)
![Commit activity](https://img.shields.io/github/commit-activity/m/mobilefirstllc/extension-cli)
![Last commit](https://img.shields.io/github/last-commit/mobilefirstllc/extension-cli)


**Extension CLI is a command-line application that facilitates rapid chrome extension development by providing
a systematic way to build, test and document extension projects.**

* * *

## Features

-   **Javascript Bundling** — Compiles, bundles and minifies javascript files (supports [ES6 syntax](http://es6-features.org/))                                                                                                           

-   **CSS Bundling** — Compiles, bundles, and minifies CSS and [SASS files](https://sass-lang.com/guide)                                                                                                                                                          

-   **Linting** — Code linting using [ESLint](https://eslint.org/)                                                                                                                                                                        

-   **.zip Generation** — Generates a `.zip` file for uploading to [Chrome Web Store](https://chrome.google.com/webstore/category/extensions)                                                                                         

-   **Source Code Docs** — Generates code documentation using [JSDoc](https://jsdoc.app/about-getting-started.html)                                                                                                                                

-   **Unit Testing** —  Sets up a unit testing environment with [mocha](https://mochajs.org), [chai](https://www.chaijs.com/), [sinon-chrome](https://github.com/acvetkov/sinon-chrome), and [js-dom](https://github.com/rstacruz/jsdom-global) 

## Motivation

After developing multiple browser extensions, it became clear that there were several steps in the development process that stayed the same between every project. 

Instead of setting up these tasks individually for each project, it made more sense to combine everything in a utility tool that could be shared between projects. 

This approach helps with creating a common, consistent development approach between multiple projects, reduces time to get started, and makes it easier to update build tools and scripts across multiple projects as many npm packages inevitably need to be updated (frequently!).

**Issues & Feature Requests:** [Submit on Github](https://github.com/MobileFirstLLC/extension-cli/issues/new/choose)

**Maker:** [Mobile First](https://mobilefirst.me)

**License:** [MIT](https://github.com/MobileFirstLLC/extension-cli/blob/master/LICENSE)

## Getting Started & Docs

**Docs: [View Full Guide](https://oss.mobilefirst.me/extension-cli)**

#### Create new extension project

```text
npx extension-cli
```

#### Add to an existing project

```text
npm install extension-cli
```

### Commands

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### xt-build

```text
xt-build --env {prod|dev} [--config filename] [--watch]
```

Build command generates a dist/ directory that can be
debugged in the browser. When called with production env flag, `-e prod`,
this command will minify and compile a `release.zip` file that can be
uploaded to Chrome Web Store for distribution.

#### xt-clean

```text
xt-clean [--modules] [--idea] [--vscode]
```

Clean operation iterates over files and directories listed in the
project `.gitignore` file, and removes all ignored files and
directories, except `node_modules`, `.idea/`, and `.vscode`. To remove these
directories, you must explicitly pass a flag to delete each one of them.

#### extension-cli

```text
npx extension-cli
```

This command will create a new extension project and initial code files. This command takes no arguments.

#### xt-docs

```text
xt-docs [--config filename]
```

Docs command generates documentation for the project. This command uses
jsdocs syntax. See [About JSDoc](https://jsdoc.app/index.html) for more details,
including [configuration options here](https://jsdoc.app/about-configuring-jsdoc.html).
The default template for the guide is [FooDoc](https://github.com/steveush/foodoc#readme).
You can override this theme in the project by changing `opts.template` in jsdoc config file.

By default, this command will automatically look for configuration in the project `package.json`.
Use `"xtdocs"` key to define config options in `package.json`. Alternatively add a separate
configuration file `.xtdocs.json` in the project root; or explicitly provide a path to a config file.
If you want to define configuration in some other location, use `-c` / `--config` flag
to provide path and name of the configuration file.

#### xt-sync

```text
xt-sync [--gitignore] [--eslint] [--gitlab] [--travis] [--all]
```

The purpose of this command is to upgrade configuration files of
a stale project to latest version, where this CLI tool will provide
updated project configuration files. If the config files have been
modified heavily for the project, it is not advisable to upgrade them
in this manner. Instead you should upgrade such configs manually.

#### xt-test

```text
xt-test [--coverage] [--watch]
```

This command will run project unit tests located in `./test` directory.

Command sets up extension unit testing environment with ES6 syntax support that is pre-initialized
with [mocha](https://mochajs.org/), [chai](https://www.chaijs.com/) (including chai-as-promised)
and expect. [nyc](https://www.npmjs.com/package/nyc) is used for computing code coverage.
The following browser APIs are also initialized: `window`, `chrome`. Window
is setup using [jsdom-global](https://www.npmjs.com/package/jsdom-global) and
chrome using [sinon-chrome](https://www.npmjs.com/package/sinon-chrome).

You may extend this test environment within a single project. This is simply the base setup
for running unit tests. Or create your own testing environment at project level if this is not suitable.

## CLI User: Read the Docs!

**[View Complete User Guide →](https://oss.mobilefirst.me/extension-cli/)**

## CLI Developer Guide

If you are interested in extending this project or making your own fork **[see this guide &rarr;](https://oss.mobilefirst.me/extension-cli/13-cli-development/)**
