---
url: https://wordpress.org/documentation/article/template-part-block
scraped_at: 2025-10-20T02:07:07.746Z
---

[Skip to content](https://wordpress.org/documentation/article/template-part-block/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[Documentation](https://wordpress.org/documentation)

Template Part block

[Home](https://wordpress.org/documentation)[Customization](https://wordpress.org/documentation/customization/)[Theme blocks](https://wordpress.org/documentation/category/theme-blocks/)Template Part block

Search documentation

# Template Part block

## In this article

Table of Contents

- [Adding template parts](https://wordpress.org/documentation/article/template-part-block/#adding-template-parts)
  - [Choosing from existing template parts](https://wordpress.org/documentation/article/template-part-block/#choosing-from-existing-template-parts)
  - [Creating new template parts](https://wordpress.org/documentation/article/template-part-block/#creating-new-template-parts)
  - [Creating new template parts from the template part list](https://wordpress.org/documentation/article/template-part-block/#creating-new-template-parts-from-the-template-part-list)
  - [Importing widget area](https://wordpress.org/documentation/article/template-part-block/#importing-widget-area)
  - [Managing template parts and patterns](https://wordpress.org/documentation/article/template-part-block/#managing-template-parts-and-patterns)
- [Customizing template parts](https://wordpress.org/documentation/article/template-part-block/#customizing-template-parts)
  - [Template part focus mode](https://wordpress.org/documentation/article/template-part-block/#template-part-focus-mode)
  - [Replacing one template part with another](https://wordpress.org/documentation/article/template-part-block/#replacing-one-template-part-with-another)
- [Advanced Settings](https://wordpress.org/documentation/article/template-part-block/#advanced-settings)
- [Changelog](https://wordpress.org/documentation/article/template-part-block/#changelog)

[↑ Back to top](https://wordpress.org/documentation/article/template-part-block/#wp--skip-link--target)

[Go back to the list of **Blocks**](https://wordpress.org/documentation/article/blocks/)

The _Template Part block_ is an advanced block introduced in WordPress 5.9 that can be used with a block theme or a theme that supports [template editing](https://wordpress.org/themes/tags/template-editing/). They often come with your theme and are used to organize and display your site structure. You can only use them while creating and editing templates to manage blocks in areas repeated across the website. For context, this block is best used to create areas like your site header and site footer. When you change blocks inside a template part, the editor updates the blocks on every block template that includes the template part.

In order to add a _Template Part block_, click on the add block button and select the _Template Part block_. You can also type _“/template part”_ and hit enter in a new paragraph block to add one quickly. In many cases, you’ll also see options to select types of Template Part blocks, like Header and Footer when searching for this block. You can search for the header or footer in the block inserter to insert the blocks or use the shortcuts _“/header”_ and _“/footer”._

_Detailed instructions on adding blocks can be found [here](https://wordpress.org/documentation/article/adding-a-new-block/)._

## [Adding template parts](https://wordpress.org/documentation/article/template-part-block/\#adding-template-parts)

You can add templates when using the [Template Editor](https://wordpress.org/documentation/article/template-editor/) or [Site Editor](https://wordpress.org/documentation/article/site-editor/) to edit templates directly. After adding a template part, you can choose from existing parts or create a new template part:

![Template part block provides two buttons: "choose" and "start blank". ](https://wordpress.org/documentation/files/2023/08/adding-template-part-block.png)

### [Choosing from existing template parts](https://wordpress.org/documentation/article/template-part-block/\#choosing-from-existing-template-parts)

Selecting the button “Choose” opens a modal where you can search, preview, and select existing parts. These parts will depend on what your theme has provided:

![Using the "choose button", existing template parts can be selected. ](https://wordpress.org/documentation/files/2023/08/choosing-template-part-1024x752.png)

### [Creating new template parts](https://wordpress.org/documentation/article/template-part-block/\#creating-new-template-parts)

Selecting “Start blank” will prompt you to add a name. It’s best to pick a descriptive name so that it’s easy to find in the future:

![When we create a new template part block, we get a field to edit the name and options to create or cancel. ](https://wordpress.org/documentation/files/2022/01/Screen-Shot-2022-01-05-at-12.12.43-PM.png)Click on the “start blank” button to place the block and begin customizing.

### [Creating new template parts from the template part list](https://wordpress.org/documentation/article/template-part-block/\#creating-new-template-parts-from-the-template-part-list)

If you are using a block theme, you can also create a new template part from the template part list in Administration Screen > Appearance > Editor > Patterns > Template Parts. Click on the Create patterns icon to find Create template part:

![Template part list area also provides an option to create template part. ](https://wordpress.org/documentation/files/2023/08/creating-new-template-part-770x1024.png)Creating template part from Patterns area

When you select the Create template part, a modal appears where you can add a name and select the area for the template part. You must provide a name in order to create a new template part:

![Upon clicking on create template part, a pop up appears with the title "Create a template part".](https://wordpress.org/documentation/files/2022/01/Screen-Shot-2022-01-05-at-12.19.00-PM-982x1024.png)

### [Importing widget area](https://wordpress.org/documentation/article/template-part-block/\#importing-widget-area)

If you’ve switched from a classic theme to a block theme and widgets created in the classic theme, you can import them from Import Widget Area dropdown in the Advanced Settings. Select the widget from dropdown and click Import.

![Import Widget Area menu in the sidebar.](https://wordpress.org/documentation/files/2024/02/importing-widget-area_6.4-1024x588.jpg)Screenshot

### [Managing template parts and patterns](https://wordpress.org/documentation/article/template-part-block/\#managing-template-parts-and-patterns)

At the bottom of the patterns screen, there is an option to manage all template parts. From you can create new template parts, or rename, delete and reset customizations made to the template parts.

![At the bottom of template part list, there is a link named "manage all template parts" which opens this list of template parts.](https://wordpress.org/documentation/files/2023/08/managing-template-parts-1024x355.png)

## [Customizing template parts](https://wordpress.org/documentation/article/template-part-block/\#customizing-template-parts)

After adding or selecting a _Template Part block_, you can customize in various ways by adding additional blocks within it. To make it easier to find current template parts to edit, it’s recommended that you use one of the following options:

- Use [List View](https://wordpress.org/documentation/article/list-view/) when you’re editing a template to quickly identify the Headers and Footers in your content to edit.
- Use the template part focus mode described below.

### [Template part focus mode](https://wordpress.org/documentation/article/template-part-block/\#template-part-focus-mode)

To make it easier to focus specifically on editing a single template part, like a Header or Footer, you can use a dedicated mode that only shows an individual template part. To access this mode, Select the template part and click Edit from the toolbar.

### [Replacing one template part with another](https://wordpress.org/documentation/article/template-part-block/\#replacing-one-template-part-with-another)

If the theme has more than one patterns for the same template part area, you will see a pattern selector in the template inspector panel. If you don’t see this selector, this is because the theme hasn’t provided multiple patterns for the same area.

## [Advanced Settings](https://wordpress.org/documentation/article/template-part-block/\#advanced-settings)

Under Advanced settings, you can rename the template part and select an area: General, header, or footer. The panel also lets you change the HTML element and add CSS class(es) to your block. You can choose between these HTML elements: Div, header, footer, main, section, article, and aside.

![Image of advanced options with the template part block.](https://wordpress.org/documentation/files/2022/01/Screen-Shot-2022-01-05-at-12.30.36-PM.png)

## [Changelog](https://wordpress.org/documentation/article/template-part-block/\#changelog)

- Updated 2024-09-23
  - Updated Replacing one template part with another
- Updated 2024-02-18
  - Swapped block action places between Replace and Edit
- Updated 2023-08-04














  - [Sort template parts by type in navigation screen](https://github.com/WordPress/gutenberg/pull/50841).
  - I have added screenshot that depicts the sorting under a new section that I created i.e **Creating new template parts from the template part list**
  - [Add corresponding area icon to template part menu items](https://github.com/WordPress/gutenberg/pull/52102).
  - I noticed the library has been replaced by Pattern so the screenshot from the section **Creating new template parts from the template part list** covers this as well.
  - [Library: Rename template parts to library](https://github.com/WordPress/gutenberg/pull/50769).
  - I noticed this PR is dated as May 19th and the one [52102](https://github.com/WordPress/gutenberg/pull/52102) was on June 29th so I am assuming the one dated with June 29th is the latest one. Is that correct?
  - [Add chevrons to the templates and template parts in site editor](https://github.com/WordPress/gutenberg/pull/50076) and
  - [Change “Browse all templates” to “Manage all templates” in template details popover](https://github.com/WordPress/gutenberg/pull/48496)

    In the section **Creating new template parts from the template part list**, the screenshot shows chevron icons on the left of patterns and on the right of manage all template parts and manage all patterns. Since there is no description of template, I didn’t add screenshot for template’s chevron icon. In the same screenshot, the manage all template parts is shown.

  - [Add “Added by” description to template part navigation sidebar](https://github.com/WordPress/gutenberg/pull/48732)

    I created this section **Managing template parts and patterns**, and there I added a screenshot that shows the Added by for template parts.

  - [Update Template Parts icon to use the symbol](https://github.com/WordPress/gutenberg/pull/50410)

    I updated the screenshots to show the latest Template parts icon
- Created: 2022-01-05

## Was this article helpful? How could it be improved? [Cancel reply](https://wordpress.org/documentation/article/template-part-block/\#respond)

[Log in to submit feedback](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fwordpress.org%2Fdocumentation%2Farticle%2Ftemplate-part-block%2F&locale=en_US). If you need support with something that wasn't covered by this article, please post your question in the [support forums](https://wordpress.org/support/forums/).

First published

January 5, 2022

Last updated

September 23, 2024

## Get more help

[Support forums](https://wordpress.org/support/forums/)

Ask questions in the support forums.

[Developers](https://developer.wordpress.org/)

Check out the developer documentation.

[Content suggestions](https://github.com/WordPress/Documentation-Issue-Tracker/issues)

Report an error or change in the documentation issue tracker.

[Get involved](https://make.wordpress.org/docs/)

Learn about the Documentation Team and how to contribute.