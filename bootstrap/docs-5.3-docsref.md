---
url: https://getbootstrap.com/docs/5.3/docsref
scraped_at: 2025-10-20T02:29:26.759Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/docsref/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/docsref/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/docsref.mdx "View and edit this file on GitHub")

# Docs reference

Examples of Bootstrap’s documentation-specific components and styles.

On this page
**On this page**

* * *

## Buttons [Link to this section: Buttons](https://getbootstrap.com/docs/5.3/docsref/\#buttons)

Primary buttonAccent buttonLight button

## Callouts [Link to this section: Callouts](https://getbootstrap.com/docs/5.3/docsref/\#callouts)

Default callout

Warning callout

Danger callout

## Code example [Link to this section: Code example](https://getbootstrap.com/docs/5.3/docsref/\#code-example)

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