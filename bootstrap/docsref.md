---
url: https://getbootstrap.com/docsref
scraped_at: 2025-10-20T02:37:17.077Z
---

[Skip to main content](https://getbootstrap.com/docsref/#content) [Skip to docs navigation](https://getbootstrap.com/docsref/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/docsref.mdx "View and edit this file on GitHub")

# Docs reference

Examples of Bootstrap’s documentation-specific components and styles.

On this page
**On this page**

* * *

## Buttons [Link to this section: Buttons](https://getbootstrap.com/docsref/\#buttons)

Primary buttonAccent buttonLight button

## Callouts [Link to this section: Callouts](https://getbootstrap.com/docsref/\#callouts)

Default callout

Warning callout

Danger callout

## Code example [Link to this section: Code example](https://getbootstrap.com/docsref/\#code-example)

```scss
.test {
  --color: blue;
}

```

The HTML abbreviation element.

This is a test.

html

```html
<div class="test">This is a test.</div>
```

[scss/\_variables.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_variables.scss)

```scss
$gradient: linear-gradient(180deg, rgba($white, .15), rgba($white, 0));

```

[site/src/assets/partials/snippets.js](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/assets/partials/snippets.js)

```js
const toastTrigger = document.getElementById('liveToastBtn')
const toastLiveExample = document.getElementById('liveToast')

if (toastTrigger) {
  const toastBootstrap = bootstrap.Toast.getOrCreateInstance(toastLiveExample)
  toastTrigger.addEventListener('click', () => {
    toastBootstrap.show()
  })
}

```