---
url: https://wordpress.org/documentation/article/custom-html
scraped_at: 2025-10-20T02:07:26.850Z
---

[Skip to content](https://wordpress.org/documentation/article/custom-html/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Custom HTML

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Widget blocks](https://wordpress.org/documentation/category/widget-blocks/)Custom HTML

Search documentation

# Custom HTML

## In this article

Table of Contents

- [Block Settings Panel](https://wordpress.org/documentation/article/custom-html/#block-settings-panel)
- [Changelog](https://wordpress.org/documentation/article/custom-html/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/custom-html/#wp--skip-link--target)

**Hypertext Markup Language (HTML)**, is language used to describe the semantic content of web pages. This can be added using the _custom HTML block_. This block allows you to insert your code so you can fine-tune your content.

The custom HTML block is for raw HTML only; for example, shortcode is not parsed in this block. It attempts to render any valid HTML. However, if a user lacks the `unfiltered_html` capability (e.g., Contributor), WordPress will sanitize the content using `[wp\_kses()](https://developer.wordpress.org/reference/functions/wp_kses/)`, stripping disallowed tags like `<script>`, `<iframe>`, etc.

In order to add a _custom HTML block_, click on the **Block Inserter** icon.

You can also type /html and hit enter in a new paragraph block to add one quickly.

![](https://user-images.githubusercontent.com/1508963/164263756-13d7432b-f385-4953-bcdb-73e8122ef430.png)HTML block add typing

[Detailed instructions on adding blocks](https://wordpress.org/documentation/article/adding-a-new-block/)

Editing the Block

Once you [add the block](https://wordpress.org/documentation/article/wordpress-editor/#adding-a-block), you can add your code and view it right from the block options. You also have all the standard block options.

![](https://user-images.githubusercontent.com/1508963/164263762-91c8b6d3-985e-4b45-b908-cde86309fc05.png)

Preview block

![Preview option in HTML block](https://user-images.githubusercontent.com/1508963/164263768-4e6a6c16-8e7c-4186-af0e-62464c6daf6c.png)Preview option in HTML block

More Options

These controls give you the option to copy, duplicate, and edit your block as HTML.

[Read about these and other settings.](https://wordpress.org/documentation/article/more-options/)

## [Block Settings Panel](https://wordpress.org/documentation/article/custom-html/\#block-settings-panel)

While most blocks have specific options in the editor sidebar in addition to the options found in the block toolbar, the HTML block does not have extra options.

![Block settings  for the custom HTML block](https://user-images.githubusercontent.com/1508963/164263778-594309aa-4b96-45bb-b6c7-ae650f226594.png)Block settings for the custom HTML block

## [Changelog](https://wordpress.org/documentation/article/custom-html/\#changelog)

- Updated 2025-07-21
  - Added detail HTML processing
- Updated 2022-11-26
  - Removed redudant content
  - Aligned images for mobile view
  - Added heading
- Updated 2022-04-20
  - Update screenshots to 5.9
  - Add More Options section

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/custom-html/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fcustom-html%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

March 7, 2019

Last updated

July 21, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.