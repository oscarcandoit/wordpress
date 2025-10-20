---
url: https://getbootstrap.com/docs/5.3/utilities/vertical-align
scraped_at: 2025-10-20T02:36:56.729Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/vertical-align/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/vertical-align/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/vertical-align.mdx "View and edit this file on GitHub")

# Vertical alignment

Easily change the vertical alignment of inline, inline-block, inline-table, and table cell elements.

Change the alignment of elements with the [`vertical-alignment`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) utilities. Please note that vertical-align only affects inline, inline-block, inline-table, and table cell elements.

Choose from `.align-baseline`, `.align-top`, `.align-middle`, `.align-bottom`, `.align-text-bottom`, and `.align-text-top` as needed.

To vertically center non-inline content (like `<div>` s and more), use our [flex box utilities](https://getbootstrap.com/docs/5.3/utilities/flex#align-items).

With inline elements:

baselinetopmiddlebottomtext-toptext-bottom

html

```html
<span class="align-baseline">baseline</span>
<span class="align-top">top</span>
<span class="align-middle">middle</span>
<span class="align-bottom">bottom</span>
<span class="align-text-top">text-top</span>
<span class="align-text-bottom">text-bottom</span>
```

With table cells:

|     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- |
| baseline | top | middle | bottom | text-top | text-bottom |

html

```html
<table style="height: 100px;">
  <tbody>
    <tr>
      <td class="align-baseline">baseline</td>
      <td class="align-top">top</td>
      <td class="align-middle">middle</td>
      <td class="align-bottom">bottom</td>
      <td class="align-text-top">text-top</td>
      <td class="align-text-bottom">text-bottom</td>
    </tr>
  </tbody>
</table>
```

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/vertical-align/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/vertical-align/\#sass-utilities-api)

Vertical align utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"align": (
  property: vertical-align,
  class: align,
  values: baseline top middle bottom text-bottom text-top
),

```