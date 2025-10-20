---
url: https://www.advancedcustomfields.com/resources/acf-blocks-faq
scraped_at: 2025-10-20T02:26:32.778Z
---

# ACF Blocks FAQ

Last updated Aug 17, 2023

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#frequently-asked-questions)

## Frequently Asked Questions

Link copied

Have a question about ACF Blocks that isn’t covered here? Then make sure to register for the next session of [ACF Chat Fridays](https://wpeng.in/acf-chat-fridays/), or reach out on [Twitter](https://twitter.com/wp_acf).

[Are blocks a replacement for metaboxes? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

No. Traditional field group meta boxes are still an important part of the content editing and theme development process. ACF will continue to utilize them as a tool for saving content.

[Can I make changes to the field group? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Yes. You can make changes to your field group and fields at any time. Making changes like this will not cause damage to existing blocks unless you remove fields and update blocks.

[Can I make changes to the template? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Yes. You can make changes to your block template or callback function at any time. ACF Blocks are dynamic and are rendered by the server each time they are loaded. This allows changes to block templates to be applied to all existing block content.

[Can I register a block without fields? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Yes. There are many scenarios where a block does not require any fields, such as a “latest post” block where you want to render PHP as a block.

[Is ACF Blocks included in the free version? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

ACF Blocks is a feature of [ACF PRO](https://www.advancedcustomfields.com/pro/), which also includes more fields and features to build better WordPress sites, such as the Repeater, Flexible Content, Clone, and Gallery fields, and options pages.

[Do I need to write any JavaScript? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

No. The ACF Blocks framework is 100% PHP, but you can add JavaScript if your block requires it for added functionality (a carousel slider, for example).

[Where is block data saved? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

WordPress saves block data as HTML comments in the post\_content. ACF Blocks follow suit, saving their data as a JSON object within that HTML comment.

[Can I load values from other blocks? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Yes, but we recommend against it for performance reasons. Unlike loading a value from a post or user, block values are saved in the block HTML comment found within the post\_content. This prevents the $post\_id parameter from working as expected in our template functions. If you really need to, you can load the post\_content of a given post, and then parse the blocks using the parse\_blocks() function. As mentioned above, we do not recommend doing this as it will degrade site performance due to the large number of queries required.

[Do ACF blocks support native components? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Not yet, but we do plan to add support for ACF Blocks rendering your React components in an upcoming release..

[What is Gutenberg and what are blocks? _![](https://www.advancedcustomfields.com/wp-content/themes/acf/assets/images/ui-icons/plus.svg)_](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)

Introduced in WordPress 5.0, the block-based editor “Gutenberg” has transformed the way content is created. Content is now created in the unit of blocks instead of freeform text. Blocks take various forms including Paragraphs, Headings, Media, and Embeds.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#related)

## Related

Link copied

- ACF Blocks: [ACF Blocks](https://www.advancedcustomfields.com/resources/blocks/)
- Functions: [acf\_register\_block\_type()](https://www.advancedcustomfields.com/resources/acf_register_block_type/)
- ACF Blocks: [Save ACF Block Field Values to Post Meta](https://www.advancedcustomfields.com/resources/save-acf-block-values-to-post-meta/)
- ACF Blocks: [Key Concepts](https://www.advancedcustomfields.com/resources/acf-blocks-key-concepts/)
- ACF Blocks: [Create Your First ACF Block](https://www.advancedcustomfields.com/resources/create-your-first-acf-block/)

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

[Got it](https://www.advancedcustomfields.com/resources/acf-blocks-faq/#)