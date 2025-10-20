---
url: https://getbootstrap.com/docs/5.3/getting-started/contribute
scraped_at: 2025-10-20T02:33:37.238Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/getting-started/contribute/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/getting-started/contribute/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/getting-started/contribute.mdx "View and edit this file on GitHub")

# Contribute

Help develop Bootstrap with our documentation build scripts and tests.

On this page
**On this page**

* * *

## Tooling setup [Link to this section: Tooling setup](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#tooling-setup)

Bootstrap uses [npm scripts](https://docs.npmjs.com/misc/scripts/) to build the documentation and compile source files. Our [package.json](https://github.com/twbs/bootstrap/blob/v5.3.8/package.json) houses these scripts for compiling code, running tests, and more. These aren’t intended for use outside our repository and documentation.

To use our build system and run our documentation locally, you’ll need a copy of Bootstrap’s source files and Node. Follow these steps and you should be ready to rock:

1. [Download and install Node.js](https://nodejs.org/en/download/), which we use to manage our dependencies.
2. Either [download Bootstrap’s sources](https://github.com/twbs/bootstrap/archive/v5.3.8.zip) or fork and clone [Bootstrap’s repository](https://github.com/twbs/bootstrap).
3. Navigate to the root `/bootstrap` directory and run `npm install` to install our local dependencies listed in [package.json](https://github.com/twbs/bootstrap/blob/v5.3.8/package.json).

When completed, you’ll be able to run the various commands provided from the command line.

## Using npm scripts [Link to this section: Using npm scripts](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#using-npm-scripts)

Our [package.json](https://github.com/twbs/bootstrap/blob/v5.3.8/package.json) includes numerous tasks for developing the project. Run `npm run` to see all the npm scripts in your terminal. **Primary tasks include:**

| Task | Description |
| --- | --- |
| `npm start` | Compiles CSS and JavaScript, builds the documentation, and starts a local server. |
| `npm run dist` | Creates the `dist/` directory with compiled files. Uses [Sass](https://sass-lang.com/), [Autoprefixer](https://github.com/postcss/autoprefixer), and [terser](https://github.com/terser/terser). |
| `npm test` | Runs tests locally after running `npm run dist` |
| `npm run docs-serve` | Builds and runs the documentation locally. |

**Get started with Bootstrap via npm with our starter project!** Head to the [Sass & JS example](https://github.com/twbs/examples/tree/main/sass-js) template repository to see how to build and customize Bootstrap in your own npm project. Includes Sass compiler, Autoprefixer, Stylelint, PurgeCSS, and Bootstrap Icons.

## Sass [Link to this section: Sass](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#sass)

Bootstrap uses [Dart Sass](https://sass-lang.com/dart-sass/) for compiling our Sass source files into CSS files (included in our build process), and we recommend you do the same if you’re compiling Sass using your own asset pipeline. We previously used Node Sass for Bootstrap v4, but LibSass and packages built on top of it, including Node Sass, are now [deprecated](https://sass-lang.com/blog/libsass-is-deprecated/).

Dart Sass uses a rounding precision of 10 and for efficiency reasons does not allow adjustment of this value. We don’t lower this precision during further processing of our generated CSS, such as during minification, but if you chose to do so we recommend maintaining a precision of at least 6 to prevent issues with browser rounding.

## Autoprefixer [Link to this section: Autoprefixer](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#autoprefixer)

Bootstrap uses [Autoprefixer](https://github.com/postcss/autoprefixer) (included in our build process) to automatically add vendor prefixes to some CSS properties at build time. Doing so saves us time and code by allowing us to write key parts of our CSS a single time while eliminating the need for vendor mixins like those found in v3.

We maintain the list of browsers supported through Autoprefixer in a separate file within our GitHub repository. See [.browserslistrc](https://github.com/twbs/bootstrap/blob/v5.3.8/.browserslistrc) for details.

## RTLCSS [Link to this section: RTLCSS](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#rtlcss)

Bootstrap uses [RTLCSS](https://rtlcss.com/) to process compiled CSS and convert them to RTL – basically replacing horizontal direction aware properties (e.g. `padding-left`) with their opposite. It allows us only write our CSS a single time and make minor tweaks using RTLCSS [control](https://rtlcss.com/learn/usage-guide/control-directives/) and [value](https://rtlcss.com/learn/usage-guide/value-directives/) directives.

## Local documentation [Link to this section: Local documentation](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#local-documentation)

Running our documentation locally requires the use of Astro. Astro is a modern static site generator that allows us to build our documentation with a combination of Markdown and React components. Here’s how to get it started:

1. Run through the [tooling setup](https://getbootstrap.com/docs/5.3/getting-started/contribute/#tooling-setup) above to install all dependencies.
2. From the root `/bootstrap` directory, run `npm run docs-serve` in the command line.
3. Open [http://localhost:9001](http://localhost:9001/) in your browser, and voilà.

Learn more about using Astro by reading its [documentation](https://docs.astro.build/en/getting-started/).

## Troubleshooting [Link to this section: Troubleshooting](https://getbootstrap.com/docs/5.3/getting-started/contribute/\#troubleshooting)

Should you encounter problems with installing dependencies, uninstall all previous dependency versions (global and local). Then, rerun `npm install`.