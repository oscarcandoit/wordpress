---
url: https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/developer-docs-bookings
scraped_at: 2025-10-20T02:26:35.091Z
---

[Skip to navigation](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/developer-docs-bookings/#main-navigation) [Skip to content](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/developer-docs-bookings/#page)

WooCommerce Bookings

- WooCommerce Bookings
  - [Getting Started](https://woocommerce.com/document/introduction-to-woocommerce-bookings/ "Getting Started")
  - [Store Manager Guide](https://woocommerce.com/document/introduction-to-woocommerce-bookings/woocommerce-bookings-store-manager-guide/ "Store Manager Guide") Expand    - [Bookings Settings](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/store-manager-guide-woocommerce-bookings/bookings-settings/ "Bookings Settings")
    - [Managing Bookings](https://woocommerce.com/document/introduction-to-woocommerce-bookings/managing-woocommerce-bookings/ "Managing Bookings")
  - [Integrations](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/integrations-woocommerce-bookings/ "Integrations") Expand    - [Elementor Connector for WooCommerce Bookings](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/integrations-woocommerce-bookings/elementor-connector-for-woocommerce-bookings/ "Elementor Connector for WooCommerce Bookings")
  - [Use Cases](https://woocommerce.com/document/introduction-to-woocommerce-bookings/woocommerce-bookings-use-cases/ "Use Cases")
  - [Bookings Developer Docs](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/developer-docs-bookings/ "Bookings Developer Docs")
  - [Bookings Availability](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/woocommerce-bookings-availability/ "WooCommerce Bookings Availability is a paid add-on for the WooCommerce Bookings extension that helps you sell more bookings by presenting a calendar or schedule of available slots in a page or post.")
  - [FAQ](https://woocommerce.com/document/introduction-to-woocommerce-bookings/bookings-faq/ "FAQ")
  - [Troubleshooting Bookings](https://woocommerce.com/documentation/products/extensions/woocommerce-bookings/troubleshooting-bookings/ "Troubleshooting Bookings")

# Bookings Developer Docs

* * *

## Documents

- [**Bookings REST API Reference**](https://woocommerce.com/document/bookings-rest-api-reference/)
The REST API Reference is targeted at WooCommerce Bookings 1.14.0+ only and written for developers looking to extend or customize WooCommerce Bookings. It requires an advanced understanding of PHP and WordPress development. Booking Slots Slots Properties Attribute Type Description product\_ids string Product IDs for slots you want to query. (Comma-separated IDs) category\_ids string Category IDs \[…\]

- [**Bookings Snippets: Tips and Tweaks**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/bookings-snippets/)
In this document, you will find many useful snippets for customizing the functionality of WooCommerce Bookings. To use a snippet, you can copy the contained code into your child theme‘s functions.php file. Snippets Make calendar default to first available booking By default the current month will be shown on the Bookings calendar for performance reasons. \[…\]

- [**Bookings: Action and Filter reference**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/bookings-action-and-filter-reference/)
Actions and filters listed on this page are specific to WooCommerce Bookings. Actions Available For Bookings The following table includes actions that you can use with WooCommerce Bookings. Action Args Description wc\_bookings\_updated   Fires after a new plugin version is installed. woocommerce\_admin\_booking\_data\_after\_booking\_details Int: Booking ID Fires after customer select box when viewing/editing a booking in \[…\]

- [**Creating Bookings Programatically**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/creating-bookings-programatically/)
Bookings can be created programmatically using PHP, should you wish to create a follow-up booking or bookings from other plugins. The function you use is create\_wc\_booking. The create\_wc\_booking function Thecreate\_wc\_booking function takes the following arguments: create\_wc\_booking( $product\_id, $new\_booking\_data = array(), $status = ‘confirmed’, $exact = false ) Booking Data Array The $new\_booking\_data argument is passed to \[…\]

- [**WooCommerce Bookings Calendar CSS Style Elements**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/woocommerce-bookings-calendar-css-style-elements/)
If you want to change the color scheme of the WooCommerce Bookings calendar of the customer view, you can do so by modifying a few CSS styles. If you are using a block theme you can enter custom CSS in the site editor. CSS Styles Below are the CSS styles you can use to modify \[…\]

- [**WooCommerce Bookings Helper**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/woocommerce-bookings-helper/)
The Bookings Helper plugin helps you troubleshoot the WooCommerce Bookings setup by allowing you to quickly export/import settings to a JSON file. To use the plugin, download, install, and activate the Bookings Helper plugin. Then go to Tools > Bookings Helper. Global Availability Rules Importing global availability rules will overwrite all rules. Since this is \[…\]

- [**WooCommerce Bookings Pages and Emails Customization**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/pages-and-emails-customization/)
WooCommerce Bookings template files contain the markup and template structure for Bookings-related pages and HTML emails for your store. Template files can be found within the /woocommerce-bookings/templates/ directory of the Bookings extension, and can be overridden just like WooCommerce core template files. Template List The table below contains the location and a description of each template Bookings uses. The location is relative to \[…\]

- [**Embedding Bookings Calendar on a custom page/post**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/embedding-bookings-calendar-on-a-custom-page-post/)
WooCommerce Bookings does not have a feature to embed a calendar on a single page or post. However, as a workaround, we can use the WooCommerce One Page Checkout plugin. This can be done using the shortcode \[woocommerce\_one\_page\_checkout product\_ids=”11″ template=”product-single”\] . The only issue is that it also displays other information, such as the Product’s image, title, checkout form, \[…\]

- [**Translating WooCommerce Bookings**](https://woocommerce.com/document/introduction-to-woocommerce-bookings/translating-woocommerce-bookings/)
WooCommerce Bookings can be translated into different languages by modifying the related Bookings language files, either manually or through the use of a third-party extension. You can also utilize this approach to customize the default text provided by the plugin according to your preference. How to find and edit the Bookings language files The language \[…\]


You've been here a while. Can I help?

AI Assistant

![](https://woocommerce.com/wp-content/themes/woo/images/svg/support-chat-bot-avatar.svg)

Hi there! 👋 I'm the WooCommerce Support AI Assistant. I have access to the documentation on WooCommerce.com and am happy to help. What can I do for you today?

Ask me anything!

Clearing the chat can improve our assistant’s responses by resetting the context. Be sure to copy and paste this chat somewhere safe if you’d like to reference it later.

Would you like to continue?

Cancel
Clear

- 30-day **[money-back guarantee](https://woocommerce.com/refund-policy/)**

- **[Support](https://woocommerce.com/docs/)**
teams across the world

- **[Safe and secure](https://woocommerce.com/products/woopayments/)**
online payments

×

Notifications