---
url: https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking
scraped_at: 2025-10-20T02:28:00.197Z
---

# ACF Blocks: How to Use Block Locking

Last updated Dec 4, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#overview)

## Overview

Link copied

Locking down your [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/) with block locking ensures those blocks can’t be removed or modified in unauthorized ways. You can think of block locking as a safety mechanism, whether you’re using it on a client’s WordPress site or one of your own. In this tutorial, we’ll show you how to use locking to restrict the movement and removal of individual blocks, and even patterns and templates.

In our previous tutorial on using [ACF Blocks with InnerBlocks and parent/child relationships](https://www.advancedcustomfields.com/resources/acf-blocks-using-innerblocks-and-parent-child-relationships/), we built a custom **Author Info** block (parent). This custom ACF Block used `InnerBlocks` to pass a series of nested blocks, which included another custom **Author Twitter** block (child).

The Author Twitter block was only available as a nested block within its parent Author Info block context. We used `"parent": [ "acf/author-info" ]` in the Author Twitter’s `block.json` file to establish this relationship and nested discoverability.

Now, we want to extend this Author Info block to refine the editorial experience for our editors. We want to make sure that they can get right to editing, and not accidentally remove or move a block and mess up the overall layout. This is where block locking is useful.

If you want to follow the steps in this tutorial exactly and already have some experience with ACF Blocks, you can [download the plugin](https://www.advancedcustomfields.com/wp-content/uploads/2023/10/author-info-block-v1.zip) created in our last tutorial and add to it as we go.

* * *

**New to ACF Blocks?** Start with our tutorial on [creating your first ACF Block!](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)

* * *

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#what-is-block-locking)

## What is Block Locking?

Link copied

WordPress provides two types of block locking: **template locking** and **individual block locking**. You can utilize either of these, or combine them for sophisticated restrictions on your blocks.

Some other considerations when using block locking in WordPress:

- Developers can use `templateLock` in their nested blocks.
- Developers can lock entire templates with `template_lock`, even when registering custom post types.
- Individual blocks can be assigned `lock` parameters in block markup. Assigned `lock` parameters can be used on the individual blocks passed into a template. The individual block’s `lock` overrides the template locking, _unless_ the template locking value is `contentOnly`.

We highly recommend reviewing this helpful video on The Key to Locking Blocks from Wes Theron of the Make WordPress Training Team, along with the [WordPress documentation](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-templates/#locking).

The key to locking blocks

![](https://videos.files.wordpress.com/OrIGvjnD/video-1457ccdc8a_mp4.scrubthumb.jpg?w=560)

Play Video

The key to locking blocks

Share Button

Play

Mute

Current Time 0:00

/

Duration 0:00

Stream Type LIVE

Chapters

Settings

Settings Menu

- Speed

1x





- 2x
- 1.75x
- 1.5x
- 1.25x
- 1x, selected
- 0.75x
- 0.5x
- 0.25x

- Quality

Auto





- 1080p
- 720p
- 480p
- 240p
- Auto

- Captions

Off





- Off, selected
- English

Picture-in-PictureFullscreen

Loaded: 0%

This is a modal window.

Beginning of dialog window. Escape will cancel and close the window.

TextColorWhiteBlackRedGreenBlueYellowMagentaCyanOpacityOpaqueSemi-TransparentText BackgroundColorBlackWhiteRedGreenBlueYellowMagentaCyanOpacityOpaqueSemi-TransparentTransparentCaption Area BackgroundColorBlackWhiteRedGreenBlueYellowMagentaCyanOpacityTransparentSemi-TransparentOpaque

Font Size50%75%100%125%150%175%200%300%400%Text Edge StyleNoneRaisedDepressedUniformDrop shadowFont FamilyProportional Sans-SerifMonospace Sans-SerifProportional SerifMonospace SerifCasualScriptSmall Caps

ResetDone

Close Modal Dialog

End of dialog window.

Close Modal Dialog

This is a modal window. This modal can be closed by pressing the Escape key or activating the close button.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#using-innerblock-template-locking)

## Using InnerBlock Template Locking

Link copied

Template locking can be accomplished by passing `templateLock` to the `InnerBlocks` component. Like this:

```php php
<?php
<InnerBlocks templateLock="all" />
```

Template locking options include the following:

- `contentOnly` — Prevents all operations. Additionally, the block types that don’t have content are hidden from the list view and can’t gain focus within the block list. Unlike the other lock types, children can’t override this.
- `all` — Prevents all operations. It is not possible to insert new blocks, move existing blocks, or delete blocks.
- `insert` — Prevents inserting or removing blocks, but allows moving blocks.

Below are screenshots of what each of these would look like when applied to our Author Info block.

![Editor with list view sidebar expanded and showing only nested content blocks with a lock icon. The result of having InnerBlock templateLock=contentOnly.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Comparing-Template-Locking-contentOnly.png)

Author Info block with `templateLock="contentOnly"` set on `InnerBlocks`.

All nested blocks that do not contain content are hidden from the list view. Only content is editable.

![Editor with list view sidebar expanded and showing all nested blocks with a lock icon. The result of having InnerBlock templateLock=all.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Comparing-Template-Locking-all.png)

Author Info block with `templateLock="all"` set on `InnerBlocks`.

All nested blocks are locked to prevent moving, deleting, or inserting new blocks.

![Editor with list view sidebar expanded and showing all nested blocks with a lock icon. Also, edit navigation expanded for nested paragraph block with option to 'Move to' highlighted. The result of having InnerBlock templateLock=insert.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Comparing-Template-Locking-insert.png)

Author Info block with `templateLock="insert"` set on `InnerBlocks`.

All nested blocks are locked from being removed or having new blocks inserted. Existing blocks can be moved.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#unlocking-one-nested-block)

### Unlocking One Nested Block

Link copied

For our Author Info block, we want to offer editors the option to remove the author’s biography paragraph, but everything else should remain locked from being removed. We’ll start by locking all the blocks down with `templateLock="all"` attribute on our InnerBlocks component, and then we’ll use individual locking properties to unlock the one nested block we want to allow them to remove. We’ll make all of our changes to the Author’s Info `template.php` file, in the `author-info` directory of the [custom plugin](https://www.advancedcustomfields.com/wp-content/uploads/2023/10/author-info-block-v1.zip) we created in our tutorial on `InnerBlocks`.

For now, we’ll update our `InnerBlocks` code as follows:

```php php
<?php
<InnerBlocks templateLock="all" />
```

Next, we’ll have to update our individual nested block to allow removal. So, if editors choose to remove the author’s biography paragraph then they have the ability.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#how-to-use-individual-block-locking)

## How to Use Individual Block Locking

Link copied

Individual block locking takes priority and overrides template locking, _unless_ `templateLock="contentOnly"` is used. This hides all blocks that do not have content from the list view, and allows editors to update _only_ the nested content block.

However, we previously decided to apply `templateLock="all"`. To update the individual Paragraph block nested within our passed template, we just need to target it with an additional `lock` parameter. Here is our abbreviated nested code before applying the parameter:

```php php
array(
    'core/paragraph',
    array(
        'style'    => array(...),
        'fontSize' => 'small',
        'content'  => 'Ea qui voluptate irure nulla aliquip nulla anim laborum exercitation eu incididunt.',
    ),
    array(),
),
```

And here it is after, with our `lock` applied:

```php php
array(
    'core/paragraph',
    array(
        'style'    => array(...),
        'fontSize' => 'small',
        'content'  => 'Ea qui voluptate irure nulla aliquip nulla anim laborum exercitation eu incididunt.',
        'lock'     => array(
            'remove' => false,
        ),
    ),
    array(),
),
```

With the `'remove' => false` above, we’re stating that the nested Paragraph block should be _allowed_ to be removed. Yes, the `false` is confusing, but this is how ya do it! 😉

Now we have our desired control of the block, with both template locking and individual block locking in place.

![Author Info block example with lines pointing to differentiated blocks.](https://www.advancedcustomfields.com/wp-content/uploads/2023/08/Hierarchy-of-Nesting.png)

Author Info block example with lines pointing to differentiated blocks.

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#next-steps-and-considerations)

## Next Steps and Considerations

Link copied

This tutorial shows how you can use block and template locking to set editorial conditions and prevent unauthorized removal or modification of your ACF Blocks, but there is a lot of room left to explore.

There is another element to curating your editorial experience, which can be utilized when placing your blocks within patterns. If you plan to leverage your ACF Blocks in the context of patterns, then you’ll want to check out [content-only block locking](https://richtabor.com/content-only/).

You could also extend your block content control strategy by preventing certain roles or users from locking and unlocking blocks. Be sure to check out how to [restrict locking and unlocking for roles](https://wpengine.com/builders/block-locking-api/#restrict-locking-unlocking), specific users, or even post types.

If you’ve been following along, your final, full plugin code should match our version: [**author-info-block-v2.zip**](https://www.advancedcustomfields.com/wp-content/uploads/2023/10/author-info-block-v2.zip)

In the next tutorial, we’ll show you how to use WordPress global styles and block styles with your ACF Blocks, providing a consistent and easy to use experience when managing settings and styles.

##### Supercharge Your Website With Premium Features Using ACF PRO

Speed up your workflow and unlock features to better develop websites using ACF Blocks and Options Pages, with the Flexible Content, Repeater,
Clone, Gallery Fields & More.


[Explore Features](https://www.advancedcustomfields.com/pro/) [View Pricing](https://www.advancedcustomfields.com/pro/#pricing-table/)

PRO Features

ACF Blocks

Options Pages

PRO Fields

Repeater

Flexible Content

Gallery

Clone

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#related)

## Related

Link copied

- ACF Blocks: [ACF Blocks: Using InnerBlocks and Parent/Child Relationships](https://www.advancedcustomfields.com/resources/acf-blocks-using-innerblocks-and-parent-child-relationships/)
- ACF Blocks: [Extending ACF Blocks With Block Supports](https://www.advancedcustomfields.com/resources/extending-acf-blocks-with-block-supports/)
- ACF Blocks: [Using Context With ACF Blocks](https://www.advancedcustomfields.com/resources/using-context-with-acf-blocks/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [ACF Blocks V3](https://www.advancedcustomfields.com/resources/acf-blocks-v3/)

Sign up for the latest Advanced Custom Fields news, updates, and developer tutorials

First name\*

Last name\*

Email\*

Anonymous ID (Segment)

GA Client ID

GA Session ID

FBC

FBP

GCLID

FBCLID

MSCLKID

LI FAT ID

Everflow Transaction ID

Kameleoon Visitor Code

UETVID

UTM Medium

UTM Content

UTM Campaign

UETSID

UTM Term

UTM Source

Logged In

MF User

Last Marketing (Form) Activity

We use cookies to offer you a better browsing experience, analyze site traffic and personalize content. Read about how we use cookies and how you can control them in our [Privacy Policy](https://wpengine.com/legal/privacy/). If you continue to use this site, you consent to our use of cookies.

[Got it](https://www.advancedcustomfields.com/resources/acf-blocks-how-to-use-block-locking/#)