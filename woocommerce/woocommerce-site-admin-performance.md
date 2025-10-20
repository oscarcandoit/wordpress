---
url: https://woocommerce.com/documentation/woocommerce/site-admin/performance
scraped_at: 2025-10-20T02:22:42.193Z
---

[Skip to navigation](https://woocommerce.com/documentation/woocommerce/site-admin/performance/#main-navigation) [Skip to content](https://woocommerce.com/documentation/woocommerce/site-admin/performance/#page)

WooCommerce

- WooCommerce
  - [Getting started](https://woocommerce.com/documentation/woocommerce/getting-started/ "Everything you’ll need to get your online store up and running. From installation to managing orders — our guides can help with configuring WooCommerce to work for your business.")
  - [Migrating to WooCommerce](https://woocommerce.com/documentation/woocommerce/migrating-to-woocommerce/ "Ready to switch platforms? Our migration guides help you confidently move your store to WooCommerce. Whether you're just exploring or already planning the transition, you'll find step-by-step resources to get set up, transfer your data, and unlock the flexibility and control that come with owning your store.")
  - [Products](https://woocommerce.com/documentation/woocommerce/core-products/ "Products") Expand    - [Adding and managing products](https://woocommerce.com/document/managing-products/ "Adding and managing products")
  - [Taxes](https://woocommerce.com/documentation/woocommerce/taxes/ "Taxes")
  - [Shipping](https://woocommerce.com/documentation/woocommerce/shipping/ "Shipping") Expand    - [Core Shipping Options](https://woocommerce.com/documentation/woocommerce/shipping/core-shipping-options/ "Core Shipping Options")
  - [Payments](https://woocommerce.com/documentation/woocommerce/payments/ "Payments")
  - [Orders](https://woocommerce.com/documentation/woocommerce/orders/ "Orders")
  - [Data and Reporting](https://woocommerce.com/documentation/woocommerce/data-reporting/ "Data and Reporting")
  - [Customers](https://woocommerce.com/documentation/woocommerce/customers/ "Customers")
  - [Marketing](https://woocommerce.com/documentation/woocommerce/marketing/ "Marketing")
  - [Site Administration](https://woocommerce.com/documentation/woocommerce/site-admin/ "Site Administration") Expand    - [Store settings](https://woocommerce.com/documentation/woocommerce/site-admin/store-settings/ "Store settings")
    - [How-to guides](https://woocommerce.com/documentation/woocommerce/site-admin/how-to/ "Helpful guides for your WooCommerce store.")
    - [Automation](https://woocommerce.com/documentation/woocommerce/site-admin/automation/ "Automation")
    - [Performance](https://woocommerce.com/documentation/woocommerce/site-admin/performance/ "Performance")
    - [Localization](https://woocommerce.com/documentation/woocommerce/site-admin/localization/ "Localization")
    - [Security](https://woocommerce.com/documentation/woocommerce/site-admin/security/ "Security")
  - [Store Design](https://woocommerce.com/documentation/woocommerce/store-design/ "Store Design") Expand    - [Classic themes](https://woocommerce.com/documentation/woocommerce/store-design/classic-themes/ "Classic themes")
    - [Block themes](https://woocommerce.com/documentation/woocommerce/store-design/block-themes-store-editing/ "Store Editing is a new paradigm for managing your store's design. Use this content to learn how the editor (and this system) works.") Expand      - [Customizing your store](https://woocommerce.com/documentation/woocommerce/store-design/block-themes-store-editing/customize-your-store/ "Check these guides for explanations on how to customize the different sections of your WooCommerce store. Note that many of these details only apply when your site is using a block theme.")
  - [Mobile App](https://woocommerce.com/documentation/woocommerce/mobile/ "Mobile App") Expand    - [Android](https://woocommerce.com/documentation/woocommerce/mobile/mobile-android/ "Android")
    - [iOS](https://woocommerce.com/documentation/woocommerce/mobile/mobile-ios/ "iOS")
  - [Get help](https://woocommerce.com/documentation/woocommerce/get-help/ "Get help with WooCommerce and WordPress by checking out our collection of guides, FAQs, and documentation.  Start here: our troubleshooting guide addresses some of the most common issues. You can also get help from your fellow merchants in the WooCommerce support forums.") Expand    - [Troubleshooting](https://woocommerce.com/documentation/woocommerce/get-help/troubleshooting-get-help/ "Not sure where to start? Check out our Troubleshooting Guide to read about common issues and their solutions.")
    - [Privacy](https://woocommerce.com/documentation/woocommerce/get-help/privacy/ "Information about what customer data may be collected and shared when a store uses extensions sold on WooCommerce.com. For information about your privacy when making purchases on WooCommerce.com, visit automattic.com/privacy.")
    - [Frequently Asked Questions](https://woocommerce.com/documentation/woocommerce/get-help/frequently-asked-questions/ "Frequently Asked Questions")

# Performance

* * *

## Documents

- [**High-Performance Order Storage**](https://woocommerce.com/document/high-performance-order-storage/)
High-Performance Order Storage (HPOS) (previously known as Custom Order Tables) is a solution specifically designed for ecommerce needs that provides a simple-to-understand, solid database structure. It uses Woo’s Create, Read, Update, Delete (CRUD) design to store order data in custom tables optimized for WooCommerce queries, with minimal impact on the store’s performance.  What’s new with High-Performance Order \[…\]

- [**Troubleshooting a slow site**](https://woocommerce.com/document/troubleshooting-a-slow-site/)
The first step for troubleshooting a slow WooCommerce site is to determine the root cause. Cache and CDN Using a caching plugin such as WP Super Cache is a good way to optimize site performance. You can also use a Content Delivery Network (CDN) such as Jetpack’s site accelerator or Cloudflare to speed your site up \[…\]

- [**WP\_options table and site speed**](https://woocommerce.com/document/wp_options-table-and-site-speed/)
When a WordPress site runs slowly, the wp\_options table is often overlooked. This table stores key site data, like permalinks, site settings, scheduled posts, and widget details.  If you have already tried the most common steps for troubleshooting a slow WooCommerce site, reviewing the wp\_options table would be a good next step. Almost every page \[…\]

- [**Problems with large amounts of data not saving (variations, rates etc)**](https://woocommerce.com/document/problems-with-large-amounts-of-data-not-saving-variations-rates-etc/)
If you notice product variations, tax rates and other large data sets not saving, Suhosin (a security module in PHP) may be preventing the POST data from being saved. This issue can also be caused by servers with version PHP 5.3.9+ and servers running mod\_security. Configuring Suhosin If enabled, Suhosin may need to be configured \[…\]

- [**Endless loading/spinner on the checkout page**](https://woocommerce.com/document/endless-loadingspinner-on-the-checkout-page/)
The ‘review order’ page loads the payment methods/totals via AJAX – this display a loading spinner briefly. If there are problems, this section may fail to load or the spinner may remain. First, you should check WooCommerce > Status for errors – often errors will be highlighted. Common causes and resolutions are listed below. AJAX \[…\]

- [**jQuery.cookie.js/jQuery.cookie.min.js scripts fail to load**](https://woocommerce.com/document/jquery-cookie-fails-to-load/)
This is a problem with the server-setting, meaning that your hosting company will need to solve this on your behalf. The problem is outdated MOD\_SECURITY core ruleset. Option 1: Get your host to update the rule set This is by far the best option as everything will then work as by design. Contact your hosting \[…\]


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