---
url: https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial
scraped_at: 2025-10-20T03:49:38.141Z
retry_attempt: 1
---

[Skip to content](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Blocks


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[How-to Guides](https://developer.wordpress.org/block-editor/how-to-guides/)Blocks

Search

# Blocks

[↑ Back to top](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/#wp--skip-link--target)

The purpose of this tutorial is to step through the fundamentals of creating a new block type. Beginning with the simplest possible example, each new section will incrementally build upon the last to include more of the common functionality you could expect to need when implementing your own block types.

To follow along with this tutorial, you can download the [accompanying WordPress plugin](https://github.com/WordPress/block-development-examples) which includes all of the examples for you to try on your own site. At each step along the way, experiment by modifying the examples with your own ideas, and observe the effects they have on the block’s behavior.

> To find the latest version of the .zip file go to the repo’s [releases page](https://github.com/WordPress/block-development-examples/releases) and look in the latest release under ‘Assets’.

Code snippets are provided in two formats “JSX” and “Plain”. JSX refers to JavaScript code that uses JSX syntax which requires a build step. Plain refers to “classic” JavaScript that does not require building. You can change between them using tabs found above each code example. Using JSX, does require you to run [the JavaScript build step](https://developer.wordpress.org/block-editor/how-to-guides/javascript/js-build-setup/) to compile your code to a browser compatible format.

Note that it is not required to use JSX to create blocks or extend the editor, you can use classic JavaScript. However, once familiar with JSX and the build step, many developers tend to find it is easier to read and write, thus most code examples you’ll find use the JSX syntax.

First published

March 9, 2021

Last updated

January 16, 2024

Edit article

[Improve it on GitHub: Blocks](https://github.com/WordPress/gutenberg/edit/trunk/docs/how-to-guides/block-tutorial/README.md)

[PreviousAccessibilityPrevious: Accessibility](https://developer.wordpress.org/block-editor/how-to-guides/accessibility/)

[NextUse styles and stylesheetsNext: Use styles and stylesheets](https://developer.wordpress.org/block-editor/how-to-guides/block-tutorial/applying-styles-with-stylesheets/)

Notifications