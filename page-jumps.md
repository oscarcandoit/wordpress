---
url: https://wordpress.org/documentation/article/page-jumps
scraped_at: 2025-10-20T02:14:19.021Z
---

[Skip to content](https://wordpress.org/documentation/article/page-jumps/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Page Jumps

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Design blocks](https://wordpress.org/documentation/category/design-blocks/)Page Jumps

Search documentation

# Page Jumps

## In this article

Table of Contents

- [Create an HTML Anchor](https://wordpress.org/documentation/article/page-jumps/#create-an-html-anchor)
  - [HTML Anchor Syntax](https://wordpress.org/documentation/article/page-jumps/#html-anchor-syntax)
- [Link to your HTML Anchor](https://wordpress.org/documentation/article/page-jumps/#link-to-your-html-anchor)
  - [Jumping to an anchor on another page](https://wordpress.org/documentation/article/page-jumps/#useful-hint)
- [Changelog](https://wordpress.org/documentation/article/page-jumps/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/page-jumps/#wp--skip-link--target)

Page jumping, also sometimes referred to as anchor links, is where you click a link and instantly get moved somewhere further up or down a page. This can be particularly useful with a long page.

One way to enable this is by setting an HTML Anchor to a Heading block on your page and creating a link that jumps to the anchor. [You can even jump to another page’s anchor](https://wordpress.org/documentation/article/page-jumps/#useful-hint).

This can also be accomplished with any other block that allows for an HTML Anchor to be set under “Advanced”. You can review which blocks have the HTML anchor field by reviewing the **[Core Blocks Reference](https://developer.wordpress.org/block-editor/reference-guides/core-blocks/)** and looking for blocks with the `anchor` attribute.

## [Create an HTML Anchor](https://wordpress.org/documentation/article/page-jumps/\#create-an-html-anchor)

![Where to add an HTML anchor for a block (Heading block) under Block settings.](https://wordpress.org/documentation/files/2022/10/190138307-c7915fea-353c-44a1-9056-a07a3af12790.png)

1. Use the Plus Icon to add a new block.
2. Select Heading as the block type, or start typing `/heading` as a shortcut (slash command) to the heading block.
3. Enter your heading text. You may leave blank in heading text if you do not want to display any text.
4. On the right side under Block Settings, click on Advanced.
5. Type a word that will become your link into the HTML Anchor field.

### [HTML Anchor Syntax](https://wordpress.org/documentation/article/page-jumps/\#html-anchor-syntax)

- HTML Anchor must be unique within a document.
- HTML Anchor is case-sensitive.
- HTML Anchor can include following symbols: hyphen(-), underscore(\_), colon(:), period(.). It cannot include space.
- HTML Anchor must start in the alphabet.

## [Link to your HTML Anchor](https://wordpress.org/documentation/article/page-jumps/\#link-to-your-html-anchor)

1. Type some text, or add an image or button that will become what you want your visitors to click on to go to another section.
2. Highlight the text, image or button, and select the link option from the block’s toolbar.
3. Type in the HTML Anchor you created, starting with the pound (#) symbol. For example, if you created an Anchor named important-notice you would link to #important-notice.

![How to add a link that jumps internally on the page to an HTML anchor.](https://wordpress.org/documentation/files/2022/10/190138761-276173ca-c970-4834-90fd-d4ee23a90218.png)

### [Jumping to an anchor on another page](https://wordpress.org/documentation/article/page-jumps/\#useful-hint)

If you want to jump to another page’s anchor, then specify URL with HTML Anchor. For example, `example.com/anotherpage#important-notice`

## [Changelog](https://wordpress.org/documentation/article/page-jumps/\#changelog)

- 2023-07-25
  - Update video URL
- 2022-10-28


  - Added a little more information about Page Jump Links use cases and other available blocks

  - Removed a note about jump links not working in Preview mode
  - Added Video walkthrough of Page Jumps
  - Updated screenshots through WordPress 6.0
  - Updated Alt text for images
- Created 2019-06-15

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/page-jumps/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fpage-jumps%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

June 15, 2019

Last updated

July 25, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.