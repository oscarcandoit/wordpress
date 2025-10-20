---
url: https://developer.wordpress.org/apis/internationalization
scraped_at: 2025-10-20T04:06:47.534Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/internationalization/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Internationalization


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)Internationalization

Search

# Internationalization

## In this article

Table of Contents

- [What is internationalization?](https://developer.wordpress.org/apis/internationalization/#what-is-internationalization)
- [Why is internationalization important?](https://developer.wordpress.org/apis/internationalization/#why-is-internationalization-important)
- [The basics](https://developer.wordpress.org/apis/internationalization/#the-basics)
- [Setting up your plugin and theme to i18n](https://developer.wordpress.org/apis/internationalization/#setting-up-your-plugin-and-theme-to-i18n)
  - [Internationalizing JavaScript](https://developer.wordpress.org/apis/internationalization/#internationalizing-javascript)
- [Internationalization Guidelines](https://developer.wordpress.org/apis/internationalization/#internationalization-guidelines)

[↑ Back to top](https://developer.wordpress.org/apis/internationalization/#wp--skip-link--target)

## [What is internationalization?](https://developer.wordpress.org/apis/internationalization/\#what-is-internationalization)

Internationalization is the process of developing your application in a way it can easily be translated into other languages. Internationalization is often abbreviated as `i18n` (because there are 18 letters between the letters i and n).

## [Why is internationalization important?](https://developer.wordpress.org/apis/internationalization/\#why-is-internationalization-important)

WordPress is used all over the world, by people who speak many different languages. The strings in WordPress need to be coded in a special way so that they can be easily translated into other languages. As a developer, you may not be able to provide localization for all your users; however, a translator can successfully localize your code without needing to modify the source code itself.

While making your code translatable is called Internationalization, the act of translating it and adapting the strings to a specific location is called [Localization](https://developer.wordpress.org/apis/handbook/internationalization/localization/). Read more about [Localization in WordPress](https://developer.wordpress.org/apis/handbook/internationalization/localization/).

## [The basics](https://developer.wordpress.org/apis/internationalization/\#the-basics)

In order to make a string translatable, you have to wrap the original strings in a call to one of the [WordPress i18n functions](https://developer.wordpress.org/apis/handbook/internationalization/internationalization-functions/).

For example, the PHP function [\_e()](https://developer.wordpress.org/reference/functions/_e/) echoes a translatable string:

``
[Copy](https://developer.wordpress.org/apis/internationalization/#)

```php
 _e('Edit post');
```

You will find code like this all over WordPress core files. However, if you are internationalizing a theme or a plugin, there is another argument that all i18n functions take called Text Domain.

Text Domains set the domain your plugin or theme translations belong. This assures there is no conflict between strings in plugins, themes, and the WordPress core.

With a text-domain, the most basic call to a i18n function that will output a string would be like:

``
[Copy](https://developer.wordpress.org/apis/internationalization/#)

```php
 _e('Edit movie', 'my-plugin');
```

## [Setting up your plugin and theme to i18n](https://developer.wordpress.org/apis/internationalization/\#setting-up-your-plugin-and-theme-to-i18n)

Setting up i18n is slightly different for Plugins and Themes, therefore this information is detailed in each respective Handbook:

- [How to internationalize your theme](https://developer.wordpress.org/themes/functionality/internationalization/)
- [How to internationalize your plugin](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/)

### [Internationalizing JavaScript](https://developer.wordpress.org/apis/internationalization/\#internationalizing-javascript)

Since WordPress 5.0 it’s possible to internationalize JavaScript files using the same set of i18n functions used in PHP.

In order to be able to use i18n functions in your JavaScript code, you have to declare `wp-i18n` as a dependency on your script when registering or enqueueing it. For example:

``
[Copy](https://developer.wordpress.org/apis/internationalization/#)

```php
wp_register_script(
     'my-script',
     plugins_url( 'js/my-script.js', FILE ),
     array( 'wp-i18n' ),
     '0.0.1'
 );
```

Now that you have added the dependency to your script, you can use i18n functions in it, however you still have to tell WordPress to load the translations.

You do this by calling `wp_set_script_translations()`. This function takes three arguments: the registered/enqueued script handle, the text domain, and optionally a path to the directory containing translation files. The latter is only needed if your plugin or theme is not hosted on WordPress.org, which provides these translation files automatically.

``
[Copy](https://developer.wordpress.org/apis/internationalization/#)

```php
wp_set_script_translations('my-script', 'my-plugin');
```

For better performance, always make sure to enqueue your scripts and load their translations only when they are really used.

In your JavaScript code you will use i18n functions pretty much the same way you do in your PHP code:

``
[Copy](https://developer.wordpress.org/apis/internationalization/#)

```js
const { __, _x, _n, sprintf } = wp.i18n;

// simple string
__( 'Hello World', 'my-plugin' );

// string with context
_x( 'My Gutenberg block name', 'block name', 'my-plugin' );
```

The available i18n for you to use in your JS code are (See internationalization functions for more details):

- [\_\_()](https://developer.wordpress.org/reference/functions/__/)
- [\_x()](https://developer.wordpress.org/reference/functions/_x/)
- [\_n()](https://developer.wordpress.org/reference/functions/_n/)
- [\_nx()](https://developer.wordpress.org/reference/functions/_nx/)
- sprintf()

Notice that the wp-i18n package also includes the `sprintf` function. This is very useful to internationalize strings that have variables in it.

Now refer to the Internationalization Guidelines to learn how to use all these functions and the best practices on writing your strings.

If you are not hosting your plugin or theme on WordPress.org, you will need to create your translation files yourself. Check [this post](https://pascalbirchler.com/internationalization-in-wordpress-5-0/) out to learn how to do this.

#### [Internationalizing JavaScript before WP 5.0](https://developer.wordpress.org/apis/internationalization/\#internationalizing-javascript-before-wp-5-0)

Another way to internationalize your JavaScript files is to use the [wp\_localize\_script()](https://developer.wordpress.org/reference/functions/wp_localize_script/) function.

With this function you can register translatable strings and have them available in your JavaScript to be used.

Please refer to the [`wp_localize_script`() reference](https://developer.wordpress.org/reference/functions/wp_localize_script/) to learn how to use it.

## [Internationalization Guidelines](https://developer.wordpress.org/apis/internationalization/\#internationalization-guidelines)

Now that you are ready to internationalize your application, read through the [Internationalization Guidelines](https://developer.wordpress.org/apis/handbook/internationalization/internationalization-guidelines/) and learn what each i18n function is for, how to use them, and the best practices when writing your strings.

First published

October 31, 2019

Last updated

November 27, 2023

[PreviousDatabase APIPrevious: Database API](https://developer.wordpress.org/apis/database/)

[NextInternationalization FunctionsNext: Internationalization Functions](https://developer.wordpress.org/apis/internationalization/internationalization-functions/)

Notifications