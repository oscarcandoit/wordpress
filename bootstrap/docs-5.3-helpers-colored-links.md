---
url: https://getbootstrap.com/docs/5.3/helpers/colored-links
scraped_at: 2025-10-20T02:34:24.868Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/colored-links/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/colored-links/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/colored-links.mdx "View and edit this file on GitHub")

# Colored links

Colored links with hover states

On this page
**On this page**

* * *

## Link colors [Link to this section: Link colors](https://getbootstrap.com/docs/5.3/helpers/colored-links/\#link-colors)

You can use the `.link-*` classes to colorize links. Unlike the [`.text-*` classes](https://getbootstrap.com/docs/5.3/utilities/colors), these classes have a `:hover` and `:focus` state. Some of the link styles use a relatively light foreground color, and should only be used on a dark background in order to have sufficient contrast.

**Heads up!** `.link-body-emphasis` is currently the only colored link that adapts to color modes. It’s treated as a special case until v6 arrives and we can more thoroughly rebuild our theme colors for color modes. Until then, it’s a unique, high-contrast link color with custom `:hover` and `:focus` styles. However, it still responds to the new link utilities.

[Primary link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Secondary link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Success link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Danger link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Warning link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Info link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Light link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Dark link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Emphasis link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

html

```html
<p><a href="#" class="link-primary">Primary link</a></p>
<p><a href="#" class="link-secondary">Secondary link</a></p>
<p><a href="#" class="link-success">Success link</a></p>
<p><a href="#" class="link-danger">Danger link</a></p>
<p><a href="#" class="link-warning">Warning link</a></p>
<p><a href="#" class="link-info">Info link</a></p>
<p><a href="#" class="link-light">Light link</a></p>
<p><a href="#" class="link-dark">Dark link</a></p>
<p><a href="#" class="link-body-emphasis">Emphasis link</a></p>
```

**Accessibility tip:** Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies like screen readers. Please ensure the meaning is obvious from the content itself (e.g., the visible text with a [_sufficient_ color contrast](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#color-contrast)) or is included through alternative means, such as additional text hidden with the `.visually-hidden` class.

## Link utilities [Link to this section: Link utilities](https://getbootstrap.com/docs/5.3/helpers/colored-links/\#link-utilities)

Added in v5.3.0

Colored links can also be modified by our [link utilities](https://getbootstrap.com/docs/5.3/utilities/link/).

[Primary link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Secondary link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Success link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Danger link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Warning link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Info link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Light link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Dark link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

[Emphasis link](https://getbootstrap.com/docs/5.3/helpers/colored-links/#)

html

```html
<p><a href="#" class="link-primary link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Primary link</a></p>
<p><a href="#" class="link-secondary link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Secondary link</a></p>
<p><a href="#" class="link-success link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Success link</a></p>
<p><a href="#" class="link-danger link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Danger link</a></p>
<p><a href="#" class="link-warning link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Warning link</a></p>
<p><a href="#" class="link-info link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Info link</a></p>
<p><a href="#" class="link-light link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Light link</a></p>
<p><a href="#" class="link-dark link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Dark link</a></p>
<p><a href="#" class="link-body-emphasis link-offset-2 link-underline-opacity-25 link-underline-opacity-75-hover">Emphasis link</a></p>
```