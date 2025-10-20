---
url: https://wordpress.org/documentation/article/details-block
scraped_at: 2025-10-20T02:14:53.303Z
---

[Skip to content](https://wordpress.org/documentation/article/details-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Details block

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Text blocks](https://wordpress.org/documentation/category/text-blocks/)Details block

Search documentation

# Details block

## In this article

Table of Contents

- [Block toolbar](https://wordpress.org/documentation/article/details-block/#block-toolbar)
  - [Transform to](https://wordpress.org/documentation/article/details-block/#transform-to)
  - [Drag](https://wordpress.org/documentation/article/details-block/#drag)
  - [Move](https://wordpress.org/documentation/article/details-block/#move)
  - [Change alignment](https://wordpress.org/documentation/article/details-block/#change-alignment)
  - [Options](https://wordpress.org/documentation/article/details-block/#options)
- [Settings](https://wordpress.org/documentation/article/details-block/#settings)
  - [Open by default](https://wordpress.org/documentation/article/details-block/#open-by-default)
  - [Advanced](https://wordpress.org/documentation/article/details-block/#advanced)
- [Styles](https://wordpress.org/documentation/article/details-block/#styles)
  - [Color](https://wordpress.org/documentation/article/details-block/#color)
  - [Typography](https://wordpress.org/documentation/article/details-block/#typography)
  - [Dimensions](https://wordpress.org/documentation/article/details-block/#dimensions)
  - [Border](https://wordpress.org/documentation/article/details-block/#border)
- [Changelog](https://wordpress.org/documentation/article/details-block/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/details-block/#wp--skip-link--target)

[Go to the list of Blocks](https://wordpress.org/documentation/article/blocks/)

The **Details block** displays a text summary and an arrow button: When you click on the text or the button, the block opens and reveals additional content on the page.

This block provides a way to show or hide content on your site. This can be useful on faq pages, showing /hiding detailed event information etc.

The **Summary** is customizable by selecting the “Write summary…” placeholder text and adding your own text. By default, the block uses the summary content as its label, similar to how the Heading block works.

The additional contentare blocks that you place inside the Details block that are hidden until you click on the summary text or the button. Because the content is hidden until you open the block, it is referred to as “hidden content”.

**Closed state:**

![The details block is closed and the icon in the arrow button points towards the summary text.](https://wordpress.org/documentation/files/2023/07/63-summary-closed.png)

**Open state:**

![The details block is open and the arrow icon points towards the content  below the summary,](https://wordpress.org/documentation/files/2023/07/63-summary-open.png)

To add a **Details** block, click on the **Block Inserter** (+)  and select the **Details** block.

You can also type `/details` and hit `enter` in a new paragraph block to add one quickly.

![using the slash inserter.](https://wordpress.org/documentation/files/2023/07/63-details-slash-inserter.png)Using the slash inserter

## [Block toolbar](https://wordpress.org/documentation/article/details-block/\#block-toolbar)

Every block comes with unique toolbar icons and block-specific user controls that allow you to manipulate the block right in the editor.

The **Details** block shows five buttons in the block toolbar:

- Transform to
- Drag icon
- Move arrows
- Change alignment
- Options

![Block toolbar for the Details block](https://wordpress.org/documentation/files/2023/07/63-details-toolbar.png)

### [Transform to](https://wordpress.org/documentation/article/details-block/\#transform-to)

![Block toolbar with transformation options.](https://wordpress.org/documentation/files/2023/07/63-details-toolbar-transform-to.png)

Click on the transform button to place the block inside a group or columns block.

### [Drag](https://wordpress.org/documentation/article/details-block/\#drag)

![Block toolbar with drag option.](https://wordpress.org/documentation/files/2023/07/63-details-toolbar-drag.png)

To drag and drop the block to a new location on the page template, click and hold the rectangle of dots, then drag to the new location. The blue separator line indicates where the block will be placed. Release the left mouse button when you find the new location to place the block.

### [Move](https://wordpress.org/documentation/article/details-block/\#move)

![Block toolbar with move options.](https://wordpress.org/documentation/files/2023/07/63-details-toolbar-move-arrows.png)

The up and down arrow icons can be used to move the block up and down on the page.

Detailed instructions on moving a block within the editor can be found [here](https://wordpress.org/documentation/article/moving-blocks/).

### [Change alignment](https://wordpress.org/documentation/article/details-block/\#change-alignment)

![Block toolbar with align options.](https://wordpress.org/documentation/files/2023/07/63-details-toolbar-align.png)

Change the alignment of the block to none, wide, or full width.

### [Options](https://wordpress.org/documentation/article/details-block/\#options)

The Options menu represented by three vertical dots on the far right of the toolbar gives you more features such as the ability to duplicate or remove the block.

Details about **More options** can be found in this [support article](https://wordpress.org/documentation/article/more-options/).

## [Settings](https://wordpress.org/documentation/article/details-block/\#settings)

The block settings panel contains customization options specific to the block. To open it, select the block and click the **Settings** button next to the **Publish** button.

![To open it, select the block and click the Settings button next to the Publish button.](https://wordpress.org/documentation/files/2023/07/63-details-settings-button.png)

![The Details block settings sidebar.](https://wordpress.org/documentation/files/2023/07/63-details-settings.png)

### [Open by default](https://wordpress.org/documentation/article/details-block/\#open-by-default)

Enabling this option keeps the block open and the hidden content will be disaplay until closed.

### [Advanced](https://wordpress.org/documentation/article/details-block/\#advanced)

![Advanced tab with HTML anchor, additional CSS and name attribute](https://wordpress.org/documentation/files/2023/08/details-advanced-6.8.png)

#### [HTML anchor](https://wordpress.org/documentation/article/details-block/\#html-anchor)

This settings let you make a unique anchor text for the Group block and link it to another web page. For more detail, refer to [Page Jumps](https://wordpress.org/documentation/article/page-jumps/).

#### [Additional CSS class(es)](https://wordpress.org/documentation/article/details-block/\#additional-css-classes)

It enables you to write custom CSS class(es) to the Group block, so you can style the block as you see fit.

#### [Name attribute](https://wordpress.org/documentation/article/details-block/\#name-attribute)

This attribute gives the name of the group of related details elements that the element is a member of. Opening one member of this group causes other members of the group to close. If the attribute is specified, its value must not be the empty string.

In below example, Summay1 and Summary2 have the same name value, and Summary3 has another one. Both Summary1 and Summary2 are synched, but Summary3 is not.

## [Styles](https://wordpress.org/documentation/article/details-block/\#styles)

![The styles tab in the Details block settings sidebar.](https://wordpress.org/documentation/files/2023/07/63-details-sidebar-styles.png)

### [Color](https://wordpress.org/documentation/article/details-block/\#color)

The block provides dimension settings options to add text, background, and link color.

For details refer to this support article: [Color settings overview](https://wordpress.org/documentation/article/colors-settings-overview/)

### [Typography](https://wordpress.org/documentation/article/details-block/\#typography)

The block provides typography settings to change the font family, appearance, line height, letter spacing, decoration, letter case, and font size.

For details refer to this support article: [Typography settings overview](https://wordpress.org/documentation/article/typography-settings-overview/)

### [Dimensions](https://wordpress.org/documentation/article/details-block/\#dimensions)

Theblock provides dimension settings options to add padding and margin.

For details refer to this support article: [Dimension settings overview](https://wordpress.org/documentation/article/dimension-controls-overview/)

### [Border](https://wordpress.org/documentation/article/details-block/\#border)

The block provides border settings options to add border color, style, width, and radius.

For details refer to this support article: [Border settings overview](https://wordpress.org/documentation/article/border-settings-overview/)

## [Changelog](https://wordpress.org/documentation/article/details-block/\#changelog)

- 2024-07-05
  - Added name attribute in advanced settings for 6.8
- 2024-06-13 Updated video to 6.5 version
- 2023-12-05 Headings case resolved
- Created 2023-08-08

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/details-block/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Fdetails-block%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

August 8, 2023

Last updated

July 5, 2025

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.