# ProXJS

Visit the ProXJS documentation for most information: [ProXJS Docs](https://proxjs.dev)

You are welcome to contribute to the docs by submitting a PR. Docs are located in the [`/packages/docs`](/packages/docs) directory.

Stay here for contribution-related information.

> Looking for legacy version docs? [Click here](https://github.com/ProgrammerKR/ProXJS/tree/v1.0.0)

<p align="center"><a href="https://proxjs.dev/patterns"><img src="/hero.jpg" alt="ProXJS Component Patterns"></a></p>

## Contribution Guide:

### Quickstart

* Clone this repo locally
* Run `npm install` & `npm run build`
* Include the `/packages/proxjs/dist/cdn.js` file from a `<script>` tag on a webpage and you're good to go!

### Brief Tour
You can get everything installed with: `npm install` in the root directory of this repo after cloning it locally.

This repo is a "mono-repo" using npm workspaces for managing the packages. Each package has its own folder in the `/packages` directory.

Rather than having to run separate builds for each package, all package bundles are handled with the same command: `npm run build`

Here's a brief look at each package in this repo:

Package | Description
--- | ---
[proxjs](packages/proxjs) | The main ProXJS repo with all of ProXJS's core
[collapse](packages/collapse) | A plugin for expanding and collapsing elements using smooth animations
[csp](packages/csp) | A repo to provide a "CSP safe" build of ProXJS
[docs](packages/docs) | The ProXJS documentation
[focus](packages/focus) | A plugin that allows you to manage focus inside an element
[history](packages/history) | A plugin for binding data to query string parameters using the history API
[intersect](packages/intersect) | A plugin for triggering JS expressions based on elements intersecting with the viewport
[mask](packages/mask) | A plugin for automatically formatting a text input field as a user types
[morph](packages/morph) | A plugin for morphing HTML (like morphdom) inside the page intelligently
[persist](packages/persist) | A plugin for persisting ProXJS state across page loads

The compiled JS files to be included as a `<script>` tag are stored in each package's `packages/[package]/dist` directory.

Each package should include:
- A "cdn" build that is self-initializing and can be included using the `src` attribute in a `<script defer>` tag
- A `module.[esm/cjs].js` file used for importing as a JS module

The bundling for ProXJS is handled exclusively by ESBuild. All of the configuration for these builds is stored in the `scripts/build.js` file.

### Testing
There are two different testing tools used in this repo: Cypress (for integration tests), and Jest (for unit tests).

All tests are stored inside the `/tests` folder under `/tests/cypress` and `/tests/jest`.

You can run them both from the command line using: `npm run test`

To open the Cypress UI (recommended during development), run: `npm run cypress`

To only run Jest tests, run `npm run jest`. You can specify CLI config options with `--` like: `npm run jest -- --watch`
