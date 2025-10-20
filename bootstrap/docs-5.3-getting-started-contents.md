---
url: https://getbootstrap.com/docs/5.3/getting-started/contents
scraped_at: 2025-10-20T02:33:34.179Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/getting-started/contents/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/getting-started/contents/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/getting-started/contents.mdx "View and edit this file on GitHub")

# Contents

Discover what’s included in Bootstrap, including our compiled and source code flavors.

On this page
**On this page**

* * *

## Compiled Bootstrap [Link to this section: Compiled Bootstrap](https://getbootstrap.com/docs/5.3/getting-started/contents/\#compiled-bootstrap)

Once downloaded, unzip the compressed folder and you’ll see something like this:

```text
bootstrap/
├── css/
│   ├── bootstrap-grid.css
│   ├── bootstrap-grid.css.map
│   ├── bootstrap-grid.min.css
│   ├── bootstrap-grid.min.css.map
│   ├── bootstrap-grid.rtl.css
│   ├── bootstrap-grid.rtl.css.map
│   ├── bootstrap-grid.rtl.min.css
│   ├── bootstrap-grid.rtl.min.css.map
│   ├── bootstrap-reboot.css
│   ├── bootstrap-reboot.css.map
│   ├── bootstrap-reboot.min.css
│   ├── bootstrap-reboot.min.css.map
│   ├── bootstrap-reboot.rtl.css
│   ├── bootstrap-reboot.rtl.css.map
│   ├── bootstrap-reboot.rtl.min.css
│   ├── bootstrap-reboot.rtl.min.css.map
│   ├── bootstrap-utilities.css
│   ├── bootstrap-utilities.css.map
│   ├── bootstrap-utilities.min.css
│   ├── bootstrap-utilities.min.css.map
│   ├── bootstrap-utilities.rtl.css
│   ├── bootstrap-utilities.rtl.css.map
│   ├── bootstrap-utilities.rtl.min.css
│   ├── bootstrap-utilities.rtl.min.css.map
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap.min.css.map
│   ├── bootstrap.rtl.css
│   ├── bootstrap.rtl.css.map
│   ├── bootstrap.rtl.min.css
│   └── bootstrap.rtl.min.css.map
└── js/
    ├── bootstrap.bundle.js
    ├── bootstrap.bundle.js.map
    ├── bootstrap.bundle.min.js
    ├── bootstrap.bundle.min.js.map
    ├── bootstrap.esm.js
    ├── bootstrap.esm.js.map
    ├── bootstrap.esm.min.js
    ├── bootstrap.esm.min.js.map
    ├── bootstrap.js
    ├── bootstrap.js.map
    ├── bootstrap.min.js
    └── bootstrap.min.js.map

```

This is the most basic form of Bootstrap: compiled files for quick drop-in usage in nearly any web project. We provide compiled CSS and JS ( `bootstrap.*`), as well as compiled and minified CSS and JS ( `bootstrap.min.*`). [Source maps](https://web.dev/articles/source-maps) ( `bootstrap.*.map`) are available for use with certain browsers’ developer tools. Bundled JS files ( `bootstrap.bundle.js` and minified `bootstrap.bundle.min.js`) include [Popper](https://popper.js.org/docs/v2/).

### CSS files [Link to this section: CSS files](https://getbootstrap.com/docs/5.3/getting-started/contents/\#css-files)

Bootstrap includes a handful of options for including some or all of our compiled CSS.

| CSS files | Layout | Content | Components | Utilities |
| --- | --- | --- | --- | --- |
| `bootstrap.css`<br>`bootstrap.min.css`<br>`bootstrap.rtl.css`<br>`bootstrap.rtl.min.css` | Included | Included | Included | Included |
| `bootstrap-grid.css`<br>`bootstrap-grid.rtl.css`<br>`bootstrap-grid.min.css`<br>`bootstrap-grid.rtl.min.css` | [Only grid system](https://getbootstrap.com/docs/5.3/layout/grid) | — | — | [Only flex utilities](https://getbootstrap.com/docs/5.3/utilities/flex) |
| `bootstrap-utilities.css`<br>`bootstrap-utilities.rtl.css`<br>`bootstrap-utilities.min.css`<br>`bootstrap-utilities.rtl.min.css` | — | — | — | Included |
| `bootstrap-reboot.css`<br>`bootstrap-reboot.rtl.css`<br>`bootstrap-reboot.min.css`<br>`bootstrap-reboot.rtl.min.css` | — | [Only Reboot](https://getbootstrap.com/docs/5.3/content/reboot) | — | — |

### JS files [Link to this section: JS files](https://getbootstrap.com/docs/5.3/getting-started/contents/\#js-files)

Similarly, we have options for including some or all of our compiled JavaScript.

| JS Files | Popper |
| --- | --- |
| `bootstrap.bundle.js`<br>`bootstrap.bundle.min.js` | Included |
| `bootstrap.js`<br>`bootstrap.min.js` | – |

## Bootstrap source code [Link to this section: Bootstrap source code](https://getbootstrap.com/docs/5.3/getting-started/contents/\#bootstrap-source-code)

The Bootstrap source code download includes the compiled CSS and JavaScript assets, along with source Sass, JavaScript, and documentation. More specifically, it includes the following and more:

```text
bootstrap/
├── dist/
│   ├── css/
│   └── js/
├── site/
│   └──content/
│      └── docs/
│          └── 5.3/
│              └── examples/
├── js/
└── scss/

```

The `scss/` and `js/` are the source code for our CSS and JavaScript. The `dist/` folder includes everything listed in the compiled download section above. The `site/content/docs/` folder includes the source code for our hosted documentation, including our live examples of Bootstrap usage.

Beyond that, any other included file provides support for packages, license information, and development.