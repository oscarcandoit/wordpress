---
url: https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin
scraped_at: 2025-10-20T03:18:54.196Z
---

[Skip to content](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

How to Internationalize Your Plugin


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Internationalization](https://developer.wordpress.org/plugins/internationalization/)How to Internationalize Your Plugin

Search

# How to Internationalize Your Plugin

## In this article

Table of Contents

- [Introduction to Gettext](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#introduction-to-gettext)
- [Text Domains](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#text-domains)
- [Domain Path](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#domain-path)
- [Basic strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#basic-strings)
- [Variables](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#variables)
- [Plurals](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#plurals)
  - [Basic Pluralization](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#basic-pluralization)
  - [Pluralization done later](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#pluralization-done-later)
- [Disambiguation by context](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#disambiguation-by-context)
- [Descriptions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#descriptions)
- [Newline characters](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#newline-characters)
- [Empty strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#empty-strings)
- [Escaping strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#escaping-strings)
- [Localization functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#localization-functions)
  - [Basic functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#basic-functions)
  - [Translate & Escape functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#translate-escape-functions)
  - [Date and number functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#date-and-number-functions)
- [Best Practices for writing strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#best-practices-for-writing-strings)
  - [Add Text Domain to strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#add-text-domain-to-strings)
- [Loading Text Domain](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#loading-text-domain)
  - [Plugins on WordPress.org](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#plugins-on-wordpress-org)
- [Handling JavaScript files](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#handling-javascript-files)
- [Language Packs](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#language-packs)

[↑ Back to top](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#wp--skip-link--target)

In order to make a string translatable in your application you have to wrap the original string in a call to one of a set of special functions. These functions collectively are known as “gettext.”

## [Introduction to Gettext](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#introduction-to-gettext)

WordPress uses the [gettext](http://www.gnu.org/software/gettext/) libraries and tools for i18n, but not directly: there are a set of special functions created just for the purpose of enabling string translation. These functions are listed below. These are the functions you should use within your plugin.

For a deeper dive into gettext, read the [gettext online manual](http://www.gnu.org/software/gettext/manual/html_node/)

## [Text Domains](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#text-domains)

Use a _text domain_ to denote all text belonging to your plugin. The text domain is a unique identifier to ensure WordPress can distinguish between all loaded translations. This increases portability and plays better with already existing WordPress tools.

The text domain must match the `slug` of the plugin. If your plugin is a single file called `my-plugin.php` or it is contained in a folder called `my-plugin` the domain name must be `my-plugin`. If your plugin is hosted on wordpress.org it must be the slug portion of your plugin URL ( `wordpress.org/plugins/` **`<slug>`**).

The text domain name must use dashes and not underscores, be lower case, and have no spaces.

The text domain also needs to be added to the plugin header. WordPress uses it to internationalize your plugin metadata even when the plugin is disabled. The text domain should be same as the one used when [loading the text domain](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#loading-text-domain).

**Header example:**

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
/*
 * Plugin Name: My Plugin
 * Author: Plugin Author
 * Text Domain: my-plugin
 */
```

Again, change “my-plugin” to the slug of your plugin.

Since WordPress 4.6 the `Text Domain` header is optional because it must be the same as the plugin slug. There is no harm in including it, but it is not required.

## [Domain Path](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#domain-path)

The domain path defines the location for a plugin’s translation. This has a few uses, notably so that WordPress knows where to find the translation even when the plugin is disabled. This defaults to the folder in which your plugin is found.

For example, if the translation is located in a folder called `languages` within your plugin, then the Domain Path is `/languages` and must be written with the first slash:

**Header example:**

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
/*
 * Plugin Name: My Plugin
 * Author: Plugin Author
 * Text Domain: my-plugin
 * Domain Path: /languages
 */
```

The `Domain Path` header can be omitted if the plugin is in the official WordPress Plugin Directory.

## [Basic strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#basic-strings)

For basic strings (meaning strings without placeholders or plurals) use `[\_\_()](https://developer.wordpress.org/reference/functions/__/)`. It returns the translation of its argument:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
__( 'Blog Options', 'my-plugin' );
```

Do not use variable names or constants for the text domain portion of a gettext function. For example: Do not do this as a shortcut:

```
__( 'Translate me.' , $text_domain );

```

To echo a retrieved translation, use `[\_e()](https://developer.wordpress.org/reference/functions/_e/)`. So instead of writing:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
echo __( 'WordPress is the best!', 'my-plugin' );
```

you can use:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
_e( 'WordPress is the best!', 'my-plugin' );
```

## [Variables](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#variables)

What if you have a string like the following:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
echo 'Your city is $city.'
```

In this case, the `$city` is a variable and should not be part of the translation. The solution is to use placeholders for the variable, along with the `printf` family of functions. Especially helpful are `[printf](http://php.net/printf)` and `[sprintf](http://php.net/sprintf)`. Here is what the right solution looks like:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	/* translators: %s: Name of a city */
	__( 'Your city is %s.', 'my-plugin' ),
	$city
);
```

Notice that here the string for translation is just the template `"Your city is %s."`, which is the same both in the source and at run-time.

Also note that there is a hint for translators so that they know the context of the placeholder.

If you have more than one placeholder in a string, it is recommended that you use [argument swapping](http://www.php.net/manual/en/function.sprintf.php#example-4829). In this case, single quotes `(')` around the string are mandatory because double quotes `(")` will tell php to interpret the `$s` as the `s` variable, which is not what we want.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	/* translators: 1: Name of a city 2: ZIP code */
	__( 'Your city is %1$s, and your zip code is %2$s.', 'my-plugin' ),
	$city,
	$zipcode
);
```

Here the zip code is being displayed after the city name. In some languages displaying the zip code and city in opposite order would be more appropriate. Using %s prefix in the above example, allows for such a case. A translation can thereby be written:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	/* translators: 1: Name of a city 2: ZIP code */
	__( 'Your zip code is %2$s, and your city is %1$s.', 'my-plugin' ),
	$city,
	$zipcode
);
```

**Important!** The following code is incorrect:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
// This is incorrect do not use.
_e( "Your city is $city.", 'my-plugin' );
```

The strings for translation are extracted from the sources, so the translators will get this phrase to translate: `"Your city is $city."`.

However in the application `_e` will be called with an argument like `"Your city is London."` and `gettext` won’t find a suitable translation of this one and will return its argument: `"Your city is London."`. Unfortunately, it isn’t translated correctly.

## [Plurals](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#plurals)

### [Basic Pluralization](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#basic-pluralization)

If you have string that changes when the number of items changes, you’ll need a way to reflect this in your translations. For example, in English you have `"One comment"` and `"Two comments"`. In other languages you can have multiple plural forms. To handle this in WordPress use the `[\_n()](https://developer.wordpress.org/reference/functions/_n/)` function.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	_n(
		'%s comment',
		'%s comments',
		get_comments_number(),
		'my-plugin'
	),
	number_format_i18n( get_comments_number() )
);
```

`_n()` accepts 4 arguments:

- singular – the singular form of the string (note that it can be used for numbers other than one in some languages, so `'%s item'` should be used instead of `'One item'`)
- plural – the plural form of the string
- count – the number of objects, which will determine whether the singular or the plural form should be returned (there are languages, which have far more than 2 forms)
- text domain – the plugins text domain

The return value of the functions is the correct translated form, corresponding to the given count.

Note that some languages use the singular form for other numbers (e.g. 21, 31 and so on, much like ’21st’, ’31st’ in English). If you would like to special case the singular, check for it specifically:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
if ( 1 === $count ) {
	printf( esc_html__( 'Last thing!', 'my-text-domain' ), $count );
} else {
	printf( esc_html( _n( '%d thing.', '%d things.', $count, 'my-text-domain' ) ), $count );
}
```

Also note that the `$count` parameter is often used twice. First `$count` is passed to `_n()` to determine which translated string to use, and then `$count` is passed to `printf()` to substitute the number into the translated string.

### [Pluralization done later](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#pluralization-done-later)

You first set the plural strings with `[\_n\_noop()](https://developer.wordpress.org/reference/functions/_n_noop/)` or `[\_nx\_noop()](https://developer.wordpress.org/reference/functions/_nx_noop/)`.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
$comments_plural = _n_noop(
	'%s comment.',
	'%s comments.'
);
```

Then at a later point in the code you can use `[translate\_nooped\_plural()](https://developer.wordpress.org/reference/functions/translate_nooped_plural/)` to load the strings.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	translate_nooped_plural(
		$comments_plural,
		get_comments_number(),
		'my-plugin'
	),
	number_format_i18n( get_comments_number() )
);
```

## [Disambiguation by context](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#disambiguation-by-context)

Sometimes one term is used in several contexts and although it is one and the same word in English it has to be translated differently in other languages. For example the word `Post` can be used both as a verb `"Click here to post your comment"` and as a noun `"Edit this post"`. In such cases the `_x()` or `_ex()` function should be used. It is similar to `__()` and `_e()`, but it has an additional argument — the context:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
_x( 'Post', 'noun', 'my-plugin' );
_x( 'Post', 'verb', 'my-plugin' );
```

Using this method in both cases we will get the string Comment for the original version, but the translators will see two Comment strings for translation, each in the different contexts.

Note that similarly to `__()`, `_x()` has an `echo` version: `_ex()`. The previous example could be written as:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
_ex( 'Post', 'noun', 'my-plugin' );
_ex( 'Post', 'verb', 'my-plugin' );
```

Use whichever you feel enhances legibility and ease-of-coding.

## [Descriptions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#descriptions)

So that translators know how to translate a string like `__( 'g:i:s a' )` you can add a clarifying comment in the source code. It has to start with the words `translators:` and to be the last PHP comment before the gettext call. Here is an example:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
/* translators: draft saved date format, see http://php.net/date */
$saved_date_format = __( 'g:i:s a' );
```

It’s also used to explain placeholders in a string like `_n_noop( '<strong>Version %1$s</strong> addressed %2$s bug.','<strong>Version %1$s</strong> addressed %2$s bugs.' )`.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
/* translators: 1: WordPress version number, 2: plural number of bugs. */
_n_noop( '<strong>Version %1$s</strong> addressed %2$s bug.','<strong>Version %1$s</strong>strong> addressed %2$s bugs.' );
```

## [Newline characters](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#newline-characters)

Gettext doesn’t like `r` (ASCII code: 13) in translatable strings, so please avoid it and use `n` instead.

## [Empty strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#empty-strings)

The empty string is reserved for internal Gettext usage and you must not try to internationalize the empty string. It also doesn’t make any sense, because the translators won’t see any context.

If you have a valid use-case to internationalize an empty string, add context to both help translators and be in peace with the Gettext system.

## [Escaping strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#escaping-strings)

It is good to escape all of your strings, this way the translators cannot run malicious code. There are a few escape functions that are integrated with internationalization functions.

## [Localization functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#localization-functions)

### [Basic functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#basic-functions)

- [\_\_()](https://developer.wordpress.org/reference/functions/__/)
- [\_e()](https://developer.wordpress.org/reference/functions/_e/)
- [\_x()](https://developer.wordpress.org/reference/functions/_x/)
- [\_ex()](https://developer.wordpress.org/reference/functions/_ex/)
- [\_n()](https://developer.wordpress.org/reference/functions/_n/)
- [\_nx()](https://developer.wordpress.org/reference/functions/_nx/)
- [\_n\_noop()](https://developer.wordpress.org/reference/functions/_n_noop/)
- [\_nx\_noop()](https://developer.wordpress.org/reference/functions/_nx_noop/)
- [translate\_nooped\_plural()](https://developer.wordpress.org/reference/functions/translate_nooped_plural()/)

### [Translate & Escape functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#translate-escape-functions)

Strings that require translation and is used in attributes of html tags must be escaped.

- [esc\_html\_\_()](https://developer.wordpress.org/reference/functions/esc_html__/)
- [esc\_html\_e()](https://developer.wordpress.org/reference/functions/esc_html_e/)
- [esc\_html\_x()](https://developer.wordpress.org/reference/functions/esc_html_x/)
- [esc\_attr\_\_()](https://developer.wordpress.org/reference/functions/esc_attr__/)
- [esc\_attr\_e()](https://developer.wordpress.org/reference/functions/esc_attr_e/)
- [esc\_attr\_x()](https://developer.wordpress.org/reference/functions/esc_attr_x/)

### [Date and number functions](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#date-and-number-functions)

- [number\_format\_i18n()](https://developer.wordpress.org/reference/functions/number_format_i18n)
- [date\_i18n()](https://developer.wordpress.org/reference/functions/date_i18n)

## [Best Practices for writing strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#best-practices-for-writing-strings)

Here are the best practices for writing strings

- Use decent English style – minimize slang and abbreviations.
- Use entire sentences – in most languages word order is different than that in English.
- Split at paragraphs – merge related sentences, but do not include a whole page of text in one string.
- Do not leave leading or trailing whitespace in a translatable phrase.
- Assume strings can double in length when translated
- Avoid unusual markup and unusual control characters – do not include tags that surround your text
- Do not put unnecessary HTML markup into the translated string
- Do not leave URLs for translation, unless they could have a version in another language.
- Add the variables as placeholders to the string as in some languages the placeholders change position.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
printf(
	__( 'Search results for: %s', 'my-plugin' ),
	get_search_query()
);
```

- Use format strings instead of string concatenation – translate phrases and not words – `printf( __( 'Your city is %1$s, and your zip code is %2$s.', 'my-plugin' ), $city, $zipcode ); ` is always better than: ` __( 'Your city is ', 'my-plugin' ) . $city . __( ', and your zip code is ', 'my-plugin' ) . $zipcode; `
- Try to use the same words and same symbols so not multiple strings needs to be translated e.g. `__( 'Posts:', 'my-plugin' );` and `__( 'Posts', 'my-plugin' );`

### [Add Text Domain to strings](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#add-text-domain-to-strings)

You must add your Text domain as an argument to every `__()`, `_e()` and `__n()` gettext call, or your translations won’t work.

Examples:

- `__( 'Post' )` should become `__( 'Post', 'my-theme' )`
- `_e( 'Post' )` should become `_e( 'Post', 'my-theme' )`
- `_n( '%s post', '%s posts', $count )` should become `_n( '%s post', '%s posts', $count, 'my-theme' )`

If there are strings in your plugin that are also used in WordPress core (e.g. ‘Settings’), you should still add your own text domain to them, otherwise they’ll become untranslated if the core string changes (which happens).

Adding the text domain by hand can be a burden if not done continuously when writing code and that’s why you can do it automatically:

- Download the `[add-textdomain.php](https://develop.svn.wordpress.org/branches/5.2/tools/i18n/add-textdomain.php)` script to the folder where the file is you want to add the text domain
- In command line move to the directory where the file is
- Run this command to create a new file with the text domain added:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```bash
php add-textdomain.php my-plugin my-plugin.php > new-my-plugin.php
```

If you wish to have the `add-textdomain.php` in a different folder you just need to define the location in the command.

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```bash
php /path/to/add-textdomain.php my-plugin my-plugin.php > new-my-plugin.php
```

Use this command if you don’t want a new file outputted:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
php add-textdomain.php -i my-plugin my-plugin.php
```

If you want to change multiple files in a directory you can also pass a directory to the script:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
php add-textdomain.php -i my-plugin my-plugin-directory
```

After it’s done, the text domain will be added to the end of all gettext calls in the file. If there is an existing text domain it will not be replaced.

## [Loading Text Domain](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#loading-text-domain)

Translations can be loaded using `load_plugin_textdomain`, for example:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
add_action( 'init', 'wpdocs_load_textdomain' );

function wpdocs_load_textdomain() {
	load_plugin_textdomain( 'wpdocs_textdomain', false, dirname( plugin_basename( __FILE__ ) ) . '/languages' );
}
```

### [Plugins on WordPress.org](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#plugins-on-wordpress-org)

Since WordPress 4.6 translations now take [translate.wordpress.org](https://translate.wordpress.org/) as priority and so plugins that are translated via translate.wordpress.org do not necessary require `load_plugin_textdomain()` anymore. If you don’t want to add a `load_plugin_textdomain()` call to your plugin you have to set the `Requires at least:` field in your readme.txt to 4.6 or more.

If you still want to load your own translations and not the ones from translate, you will have to use a hook filter named `load_textdomain_mofile`.

**Example** with a .mo file in the `/languages/` directory of your plugin, with this code inserted in the main plugin file:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#)

```php
function my_plugin_load_my_own_textdomain( $mofile, $domain ) {
	if ( 'my-domain' === $domain && false !== strpos( $mofile, WP_LANG_DIR . '/plugins/' ) ) {
		$locale = apply_filters( 'plugin_locale', determine_locale(), $domain );
		$mofile = WP_PLUGIN_DIR . '/' . dirname( plugin_basename( __FILE__ ) ) . '/languages/' . $domain . '-' . $locale . '.mo';
	}
	return $mofile;
}
add_filter( 'load_textdomain_mofile', 'my_plugin_load_my_own_textdomain', 10, 2 );
```

## [Handling JavaScript files](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#handling-javascript-files)

Check the [Internationalizing javascript](https://developer.wordpress.org/apis/handbook/internationalization/#internationalizing-javascript) section of the [Common APIs Handbook](https://developer.wordpress.org/apis/) to see how to properly load your translation files. There is also the [Gutenburg plugin docs page](https://github.com/WordPress/gutenberg/blob/trunk/docs/how-to-guides/internationalization.md).

## [Language Packs](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/\#language-packs)

If you’re interested in language packs and how the import to [translate.wordpress.org](http://translate.wordpress.org/) is working, please read the [Meta Handbook page about Translations](https://make.wordpress.org/meta/handbook/documentation/translations/).

Also refer [Plugin/Theme Authors Guide in Polyglots Handbooks](https://make.wordpress.org/polyglots/handbook/plugin-theme-authors-guide/) for getting your project translated.

First published

October 19, 2014

Last updated

March 27, 2024

[PreviousInternationalizationPrevious: Internationalization](https://developer.wordpress.org/plugins/internationalization/)

[NextInternationalization SecurityNext: Internationalization Security](https://developer.wordpress.org/plugins/internationalization/security/)

Notifications