---
url: https://getbootstrap.com/docs/5.3/utilities/interactions
scraped_at: 2025-10-20T02:36:20.159Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/utilities/interactions/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/utilities/interactions/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/utilities/interactions.mdx "View and edit this file on GitHub")

# Interactions

Utility classes that change how users interact with contents of a website.

## Text selection [Link to this section: Text selection](https://getbootstrap.com/docs/5.3/utilities/interactions/\#text-selection)

Change the way in which the content is selected when the user interacts with it.

This paragraph will be entirely selected when clicked by the user.

This paragraph has default select behavior.

This paragraph will not be selectable when clicked by the user.

html

```html
<p class="user-select-all">This paragraph will be entirely selected when clicked by the user.</p>
<p class="user-select-auto">This paragraph has default select behavior.</p>
<p class="user-select-none">This paragraph will not be selectable when clicked by the user.</p>
```

## Pointer events [Link to this section: Pointer events](https://getbootstrap.com/docs/5.3/utilities/interactions/\#pointer-events)

Bootstrap provides `.pe-none` and `.pe-auto` classes to prevent or add element interactions.

[This link](https://getbootstrap.com/docs/5.3/utilities/interactions/#) can not be clicked.

[This link](https://getbootstrap.com/docs/5.3/utilities/interactions/#) can be clicked (this is default behavior).

[This link](https://getbootstrap.com/docs/5.3/utilities/interactions/#) can not be clicked because the `pointer-events` property is inherited from its parent. However, [this link](https://getbootstrap.com/docs/5.3/utilities/interactions/#) has a `pe-auto` class and can be clicked.

html

```html
<p><a href="#" class="pe-none" tabindex="-1" aria-disabled="true">This link</a> can not be clicked.</p>
<p><a href="#" class="pe-auto">This link</a> can be clicked (this is default behavior).</p>
<p class="pe-none"><a href="#" tabindex="-1" aria-disabled="true">This link</a> can not be clicked because the <code>pointer-events</code> property is inherited from its parent. However, <a href="#" class="pe-auto">this link</a> has a <code>pe-auto</code> class and can be clicked.</p>
```

The `.pe-none` class (and the `pointer-events` CSS property it sets) only prevents interactions with a pointer (mouse, stylus, touch). Links and controls with `.pe-none` are, by default, still focusable and actionable for keyboard users. To ensure that they are completely neutralized even for keyboard users, you may need to add further attributes such as `tabindex="-1"` (to prevent them from receiving keyboard focus) and `aria-disabled="true"` (to convey the fact they are effectively disabled to assistive technologies), and possibly use JavaScript to completely prevent them from being actionable.

If possible, the simpler solution is:

- For form controls, add the `disabled` HTML attribute.
- For links, remove the `href` attribute, making it a non-interactive anchor or placeholder link.

## CSS [Link to this section: CSS](https://getbootstrap.com/docs/5.3/utilities/interactions/\#css)

### Sass utilities API [Link to this section: Sass utilities API](https://getbootstrap.com/docs/5.3/utilities/interactions/\#sass-utilities-api)

Interaction utilities are declared in our utilities API in `scss/_utilities.scss`. [Learn how to use the utilities API.](https://getbootstrap.com/docs/5.3/utilities/api#using-the-api)

[scss/\_utilities.scss](https://github.com/twbs/bootstrap/blob/v5.3.8/scss/_utilities.scss)

```scss
"user-select": (
  property: user-select,
  values: all auto none
),
"pointer-events": (
  property: pointer-events,
  class: pe,
  values: none auto,
),

```