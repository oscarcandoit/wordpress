---
url: https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content
scraped_at: 2025-10-20T02:14:15.303Z
---

[Skip to content](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Block Error: Unexpected or Invalid Content

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Block Editor](https://wordpress.org/documentation/category/block-editor/)Block Error: Unexpected or Invalid Content

Search documentation

# Block Error: Unexpected or Invalid Content

## In this article

Table of Contents

- [Error overview](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#error-overview)
- [Possible reasons a block displays an error](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#possible-reasons-a-block-displays-an-error)
  - [The option to edit the block using HTML](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#the-option-to-edit-the-block-using-html)
  - [Unexpected HTML formatting](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#unexpected-html-formatting)
  - [Plugin or Theme conflict](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#plugin-or-theme-conflict)
- [Ways to solve the error](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#ways-to-solve-the-error)
  - [Attempt Block Recovery](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#attempt-block-recovery)
  - [Resolve](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#resolve)
  - [Convert to HTML](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#convert-to-html-2)
  - [Convert to Classic Block](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#convert-to-classic-block)

[↑ Back to top](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/#wp--skip-link--target)

## [Error overview](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#error-overview)

If you’re encountering this error message in the Block Editor, it typically means that there is a problem with the content you’re trying to insert or edit within a block. Usually, the error is displayed when the affected block contains content that has a formatting problem, this could happen because of a number of reasons explained in this article.

![Picture displaying a block error ](https://wordpress.org/documentation/files/2023/06/Screenshot-2023-06-23-at-16.41.16-1024x152.png)

**More Options**

As with other blocks, the affected blocks also include the **More options** menu in the block toolbar. You can access these options by clicking on the ellipses (three dots) in the block toolbar as shown below. The **Copy Block** option allows you to copy the block and its content to a clipboard, you can paste this content elsewhere in the editor or even on a different post/page.

[Read about the More Options settings and how to make use of them](https://wordpress.org/documentation/article/more-options/)

![More options for the affected block ](https://wordpress.org/documentation/files/2023/06/more-options-block-error-1024x823.png)

## [Possible reasons a block displays an error](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#possible-reasons-a-block-displays-an-error)

### [The option to edit the block using HTML](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#the-option-to-edit-the-block-using-html)

A block’s toolbar provides an option to edit your block’s HTML code.

![Showing the option to edit a block as HTML option](https://wordpress.org/documentation/files/2023/06/edit-as-html-1024x450.png)

In this case, the error can be displayed when there is a syntax error. For example, adding two <p> opening tags before a closing tag </p> on a Paragraph block or using the wrong syntax for adding a link as shown below.

### [Unexpected HTML formatting](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#unexpected-html-formatting)

This can occur when the block editor detects a mismatch between the expected markup and the actual HTML content within a block. This error typically happens when HTML is manually added or copied into a block, and the block editor doesn’t recognize it as valid content for that specific block type.

For example, adding Javascript to a block that isn’t the [Custom HTML Block](https://wordpress.org/documentation/article/custom-html/) or in the case shown below, adding inline CSS to a paragraph block. Style attributes aren’t expected by the block so it will return an error.

### [Plugin or Theme conflict](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#plugin-or-theme-conflict)

It’s possible that a theme or plugin is interfering with the editor. Maybe your site isn’t up-to-date, you didn’t configure some important settings properly or there is some code conflicting with the blocks on the page. However, whatever the reason may be, you will need to do some troubleshooting to solve this kind of problem.

## [Ways to solve the error](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#ways-to-solve-the-error)

The block will give you several options to fix the error: Attempt Block Recovery, and an ellipsis (three-dot) button containing the options Resolve, Convert to HTML, and Convert to Classic Block.

![](https://wordpress.org/documentation/files/2023/06/resolve-the-error-1024x520.png)

You will have to be mindful of why you are receiving the error, in some cases these options will not be helpful for example when you have the wrong Syntax or you try to add Javascript or PHP code.

### [Attempt Block Recovery](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#attempt-block-recovery)

![](https://wordpress.org/documentation/files/2023/06/attempt-block-recovery--1024x361.png)

Attempt Block Recovery button will restore the block as it was before the error appeared. This option will automatically remove the custom code and revert the block back to its previous safe state.

### [Resolve](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#resolve)

![](https://wordpress.org/documentation/files/2023/06/Resolve-1024x336.png)

When you click on the ellipsis (three dots) button you will see more options, the first option is Resolve. When you choose to Resolve the block error, you will be provided with two options each with its own possible outcome.

#### [Convert to HTML](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#convert-to-html)

On the left side, you have the option to convert the block to a Custom HTML Block, this will convert the invalid content directly into an HTML block and keep any HTML customization made. You can read more about [the Custom HTML block](https://wordpress.org/documentation/article/custom-html/) in this guide.

#### [Convert to Block](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#convert-to-block)

On the right side, you can convert the HTML code to Blocks,  changes that will be made when that is done will be clearly displayed.

In the example below, converting the block to a Custom HTML block will keep the inline CSS added to change the font color to pink which would normally be stripped off by the Paragraph block.

![](https://wordpress.org/documentation/files/2023/06/resolve-options-1024x251.png)

### [Convert to HTML](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#convert-to-html-2)

The third option is to convert to a Custom HTML block, this is the same function as the Convert to HTML option which is part of the Resolve option above.

![](https://wordpress.org/documentation/files/2023/06/convert-to-html-block.png)

### [Convert to Classic Block](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#convert-to-classic-block)

![](https://wordpress.org/documentation/files/2023/06/convert-to-classic-block.png)

You can convert the invalid content into a [Classic Block](https://wordpress.org/plugins/classic-editor/),  this block contains the same options from the Classic Editor. The changes you would have made will be kept similar to converting the Custom HMTL block. You can go over [our Classic Editor guide](https://wordpress.org/documentation/article/write-posts-classic-editor/) for an explanation of each of the options shown for the Classic Block.

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/block-error-unexpected-or-invalid-content/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fblock-error-unexpected-or-invalid-content%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

June 27, 2023

Last updated

June 27, 2023

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.