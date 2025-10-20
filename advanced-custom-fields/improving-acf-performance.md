---
url: https://www.advancedcustomfields.com/resources/improving-acf-performance
scraped_at: 2025-10-20T02:33:00.179Z
---

# Improving ACF Performance

Last updated Mar 10, 2025

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#overview)

## Overview

Link copied

Clients, editors, and end users all expect the WordPress sites you build with ACF to deliver a fast and frictionless experience. In this guide, we explore several strategies to ensure ACF delivers optimal performance, including leveraging JSON sync, limiting large field groups, and paginating Repeater fields.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#test-third-party-addons)

## Test Third-Party Addons

Link copied

While it’s not the most likely cause, it’s possible that a third-party addon may be the culprit if you’re experiencing poor performance from ACF. It’s also fairly simple to test.

The first step is to establish baseline performance. Disable _all_ third-party addons, and then [test the WordPress site’s performance](https://wpengine.com/resources/wordpress-website-performance-check/) without them. If performance improves, it’s a pretty strong indicator that at least one addon is slowing down ACF.

Next, reactivate the addons one by one, testing performance each time. This should allow you to track down which addons are causing the drop in performance. At that point, it’s up to you to decide if the addon’s capabilities are worth the performance cost.

In addition, you might want to try temporarily disabling _all_ of the site’s plugins other than ACF and testing them the same way. A site with a lot of plugins running is always going to be slower than it would be without them.

Even if you do find that a third-party addon or another plugin is causing an issue, we still advise looking over the other practices outlined below. They are almost guaranteed to increase performance if you’re not using them already.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#use-acfs-local-json-feature)

## Use ACF’s Local JSON Feature

Link copied

Leveraging ACF’s [Local JSON](https://www.advancedcustomfields.com/resources/local-json/) feature is one of the most effective ways to improve the plugin’s performance. This feature allows you to save your field groups, post types, taxonomies, and option pages as JSON files within your WordPress theme, rather than storing them in the database.

The key benefit is that it reduces the number of database calls required to load your data. When ACF loads the JSON files, it can quickly retrieve the necessary settings without having to make multiple queries to the database. This results in faster page load times and improved overall performance for your WordPress site.

The Local JSON feature offers other advantages beyond performance gains:

- **Version Control:** By storing your field settings in JSON files, you can version control them using a tool like Git. This makes it much easier to track changes, collaborate with other developers, and deploy updates across different environments.

- **Customization:** Filters allow you to customize where the JSON files are saved based on the name, key, or the post type of the item being saved.


In short, using Local JSON improves performance, development workflow, and collaboration.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#lazy-loading-fields)

## Lazy Loading Fields

Link copied

[Lazy loading](https://wpengine.com/resources/wordpress-lazy-load/) is a technique that delays the loading of resources until they’re needed. It loads only the resources that are immediately visible to the user, and then loads the remaining resources as the user scrolls or interacts with the page.

When it comes to ACF fields, lazy loading can be particularly beneficial if you have a large number of custom fields on your pages.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#autoloading-on-options-pages)

## Autoloading on Options Pages

Link copied

The [options page](https://www.advancedcustomfields.com/resources/options-page/) feature found in ACF PRO saves all data in the same location by default, the `wp_options` table, rather than attaching it to a page or post. Toggling on **Autoload Options** when creating an options page in the UI – or using the `'autoload' => true` arg when registering them with code – will automatically load the field values in the option records when WordPress loads.

This can actually _improve_ performance when those field values are being accessed frequently (i.e., being used in a header or footer), since the values are being queried from the database less often. In every other case, it’s better to leave autoloading turned off or set to `false`.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#improving-performance-of-large-field-groups)

## Improving Performance of Large Field Groups

Link copied

Large field groups can impact admin performance, primarily due to the number of database queries and/or the complexity of the field groups. Using local JSON files, as described above, can help mitigate this by reducing the number of database calls.

Breaking down large field groups into smaller, more manageable groups can also help improve performance. If possible, create field groups that have a specific purpose – for example, creating a field group with a few fields for a specific page is always more performant than having a catch-all field group with a lot of fields that is reused on multiple locations.

Be discerning in cases where ACF lets you choose the return format, such as the [Image](https://www.advancedcustomfields.com/resources/image/) and [File](https://www.advancedcustomfields.com/resources/file/) fields. ACF always stores the ID as part of the field value, and then uses it to build arrays and strings. This means it will always be somewhat slower to return an array or string than the ID alone. Restricting the use of these return formats to situations where they’re truly needed can help increase performance.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#improving-performance-for-flexible-content-and-repeater-fields)

## Improving Performance for Flexible Content and Repeater Fields

Link copied

The [Flexible Content](https://www.advancedcustomfields.com/resources/flexible-content/) and [Repeater](https://www.advancedcustomfields.com/resources/repeater/) fields available in [ACF PRO](https://www.advancedcustomfields.com/pro/) are tremendously useful, but they can impact performance when they contain a lot of data. The more data, the more resources required to process it.

On the server side, increasing resources to serve content as fast as possible can help deal with large volumes of data. Your hosting provider should be able to assist you. On the client side, unfortunately, the problem is usually related to how much CPU/memory the browser has available. The only way to improve this is to limit the number of fields that are output on a particular page. Consider how many sub fields the Flexible Content or Repeater field will have, and how many layouts/repeater rows will typically be added. If there are a lot of sub fields and a lot of layouts/rows, you may start to see browser issues.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#repeater-field-pagination)

### Repeater field pagination

Link copied

When loading an edit page with a Repeater field in the WordPress admin, the default behavior of the Repeater is to load all the rows of data, and every sub field for each row. This increases the overall load time and blocks users from certain actions, such as saving the post.

Once the post is saved, ACF sends every row and sub field back to the server, even if the data hasn’t changed. This can cause memory issues, data not saving correctly, and hitting the limits of the PHP `max_input_vars` setting.

The [Pagination setting](https://www.advancedcustomfields.com/resources/repeater/#pagination) can improve performance for Repeater fields by rendering fewer rows at once. For large Repeaters, this helps avoid browser crashes and PHP errors that may occur during load or save.

Enabling pagination can improve performance, but there are a few cases where it isn’t supported. The setting won’t be displayed for any Repeaters inside other Repeaters, Flexible Content fields, or ACF Blocks.

Pagination _can_ be enabled for Repeater fields in frontend forms, but the Repeater will be displayed on the frontend as if pagination was disabled. In this case, pagination will still work when viewing the same Repeater field in the WordPress admin.

Flexible Content fields do not offer pagination at this point in time, although we hope to include it in a future release.

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#conclusion)

## Conclusion

Link copied

Implementing these strategies can help optimize how ACF performs on the WordPress sites you build. In particular, leveraging ACF’s Local JSON feature can significantly enhance the speed and efficiency of your sites, and carries additional benefits for improved collaboration and workflow.

For large field groups, as well as Repeaters and Flexible Content, the key to performance is often to limit the number of fields that are rendered at one time.

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

[Link to heading#](https://www.advancedcustomfields.com/resources/improving-acf-performance/#related)

## Related

Link copied

- Features: [Local JSON](https://www.advancedcustomfields.com/resources/local-json/)
- Videos: [ACF Unlocks the True Power of WordPress](https://www.advancedcustomfields.com/resources/acf-unlocks-the-true-power-of-wordpress/)
- Guides: [Register fields via PHP](https://www.advancedcustomfields.com/resources/register-fields-via-php/)
- Features: [Synchronized JSON](https://www.advancedcustomfields.com/resources/synchronized-json/)
- Getting Started: [Getting Started with ACF](https://www.advancedcustomfields.com/resources/getting-started-with-acf/)

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

[Got it](https://www.advancedcustomfields.com/resources/improving-acf-performance/#)