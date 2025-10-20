---
url: https://getbootstrap.com/docs/5.3/getting-started/accessibility
scraped_at: 2025-10-20T02:33:10.627Z
---

[Skip to main content](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#content) [Skip to docs navigation](https://getbootstrap.com/docs/5.3/getting-started/accessibility/#bd-docs-nav)

[View on GitHub](https://github.com/twbs/bootstrap/blob/v5.3.8/site/src/content/docs/getting-started/accessibility.mdx "View and edit this file on GitHub")

# Accessibility

A brief overview of Bootstrap’s features and limitations for the creation of accessible content.

On this page
**On this page**

* * *

Bootstrap provides an easy-to-use framework of ready-made styles, layout tools, and interactive components, allowing developers to create websites and applications that are visually appealing, functionally rich, and accessible out of the box.

## Overview and limitations [Link to this section: Overview and limitations](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#overview-and-limitations)

The overall accessibility of any project built with Bootstrap depends in large part on the author’s markup, additional styling, and scripting they’ve included. However, provided that these have been implemented correctly, it should be perfectly possible to create websites and applications with Bootstrap that fulfill [WCAG 2.2](https://www.w3.org/TR/WCAG/) (A/AA/AAA), [Section 508](https://www.section508.gov/), and similar accessibility standards and requirements.

### Structural markup [Link to this section: Structural markup](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#structural-markup)

Bootstrap’s styling and layout can be applied to a wide range of markup structures. This documentation aims to provide developers with best practice examples to demonstrate the use of Bootstrap itself and illustrate appropriate semantic markup, including ways in which potential accessibility concerns can be addressed.

### Interactive components [Link to this section: Interactive components](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#interactive-components)

Bootstrap’s interactive components—such as modal dialogs, dropdown menus, and custom tooltips—are designed to work for touch, mouse, and keyboard users. Through the use of relevant [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) roles and attributes, these components should also be understandable and operable using assistive technologies (such as screen readers).

Because Bootstrap’s components are purposely designed to be fairly generic, authors may need to include further ARIA roles and attributes, as well as JavaScript behavior, to more accurately convey the precise nature and functionality of their component. This is usually noted in the documentation.

### Color contrast [Link to this section: Color contrast](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#color-contrast)

Some combinations of colors that currently make up Bootstrap’s default palette—used throughout the framework for things such as button variations, alert variations, form validation indicators—may lead to _insufficient_ color contrast (below the recommended [WCAG 2.2 text color contrast ratio of 4.5:1](https://www.w3.org/TR/WCAG/#contrast-minimum) and the [WCAG 2.2 non-text color contrast ratio of 3:1](https://www.w3.org/TR/WCAG/#non-text-contrast)), particularly when used against a light background. Authors are encouraged to test their specific uses of color and, where necessary, manually modify/extend these default colors to ensure adequate color contrast ratios.

### Visually hidden content [Link to this section: Visually hidden content](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#visually-hidden-content)

Content which should be visually hidden, but remain accessible to assistive technologies such as screen readers, can be styled using the `.visually-hidden` class. This can be useful in situations where additional visual information or cues (such as meaning denoted through the use of color) need to also be conveyed to non-visual users.

```html
<p class="text-danger">
  <span class="visually-hidden">Danger: </span>
  This action is not reversible
</p>

```

For visually hidden interactive controls, such as traditional “skip” links, use the `.visually-hidden-focusable` class. This will ensure that the control becomes visible once focused (for sighted keyboard users). **Watch out, compared to the equivalent `.sr-only` and `.sr-only-focusable` classes in past versions, Bootstrap 5’s `.visually-hidden-focusable` is a standalone class, and must not be used in combination with the `.visually-hidden` class.**

```html
<a class="visually-hidden-focusable" href="#content">Skip to main content</a>

```

### Reduced motion [Link to this section: Reduced motion](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#reduced-motion)

Bootstrap includes support for the [`prefers-reduced-motion` media feature](https://www.w3.org/TR/mediaqueries-5/#prefers-reduced-motion). In browsers/environments that allow the user to specify their preference for reduced motion, most CSS transition effects in Bootstrap (for instance, when a modal dialog is opened or closed, or the sliding animation in carousels) will be disabled, and meaningful animations (such as spinners) will be slowed down.

On browsers that support `prefers-reduced-motion`, and where the user has _not_ explicitly signaled that they’d prefer reduced motion (i.e. where `prefers-reduced-motion: no-preference`), Bootstrap enables smooth scrolling using the `scroll-behavior` property.

## Additional resources [Link to this section: Additional resources](https://getbootstrap.com/docs/5.3/getting-started/accessibility/\#additional-resources)

- [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG/)
- [The A11Y Project](https://www.a11yproject.com/)
- [MDN accessibility documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
- [Color Contrast Analyser (CCA)](https://www.tpgi.com/color-contrast-checker/)
- ["HTML Codesniffer" bookmarklet for identifying accessibility issues](https://github.com/squizlabs/HTML_CodeSniffer)
- [Microsoft Accessibility Insights](https://accessibilityinsights.io/)
- [Deque Axe testing tools](https://www.deque.com/axe/)
- [Introduction to Web Accessibility](https://www.w3.org/WAI/fundamentals/accessibility-intro/)