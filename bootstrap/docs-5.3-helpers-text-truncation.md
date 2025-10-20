---
url: https://getbootstrap.com/docs/5.3/helpers/text-truncation
scraped_at: 2025-10-20T02:35:04.785Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/helpers/text-truncation/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/helpers/text-truncation/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/helpers/text-truncation.mdx "View and edit this file on GitHub")

# Text truncation

Truncate long strings of text with an ellipsis.

For longer content, you can add a `.text-truncate` class to truncate the text with an ellipsis. **Requires `display: inline-block` or `display: block`.**

This text is quite long, and will be truncated once displayed.


This text is quite long, and will be truncated once displayed.

html

```html
<!-- Block level -->
<div class="row">
  <div class="col-2 text-truncate">
    This text is quite long, and will be truncated once displayed.
  </div>
</div>

<!-- Inline level -->
<span class="d-inline-block text-truncate" style="max-width: 150px;">
  This text is quite long, and will be truncated once displayed.
</span>
```