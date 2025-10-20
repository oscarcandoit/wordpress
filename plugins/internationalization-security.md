---
url: https://developer.wordpress.org/plugins/internationalization/security
scraped_at: 2025-10-20T03:13:41.843Z
---

[Skip to content](https://developer.wordpress.org/plugins/internationalization/security/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Internationalization Security


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Internationalization](https://developer.wordpress.org/plugins/internationalization/)Internationalization Security

Search

# Internationalization Security

## In this article

Table of Contents

- [Check for Spam and Other Malicious Strings](https://developer.wordpress.org/plugins/internationalization/security/#check-for-spam-and-other-malicious-strings)
- [Escape Internationalized Strings](https://developer.wordpress.org/plugins/internationalization/security/#escape-internationalized-strings)
- [Use Placeholders for URLs](https://developer.wordpress.org/plugins/internationalization/security/#use-placeholders-for-urls)
- [Compile Your Own .mo Binaries](https://developer.wordpress.org/plugins/internationalization/security/#compile-your-own-mo-binaries)

[↑ Back to top](https://developer.wordpress.org/plugins/internationalization/security/#wp--skip-link--target)

Security is often overlooked when talking about internationalization, but there are a few important things to keep in mind.

### [Check for Spam and Other Malicious Strings](https://developer.wordpress.org/plugins/internationalization/security/\#check-for-spam-and-other-malicious-strings)

When a translator submits a localization to you, always check to make sure they didn’t include spam or other malicious words in their translation. You can use [Google Translate](https://translate.google.com/) to translate their translation back into your native language so that you can easily compare the original and translated strings.

### [Escape Internationalized Strings](https://developer.wordpress.org/plugins/internationalization/security/\#escape-internationalized-strings)

You can’t trust that a translator will only add benign text to their localization; if they want to, they could add malicious JavaScript or other code instead. To protect against that, it’s important to treat internationalized strings like you would any other untrusted input.

If you’re outputting the strings, then they should be escaped.

Insecure:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/security/#)

```php
_e( 'The REST API content endpoints were added in WordPress 4.7.', 'your-text-domain' );
```

Secure:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/security/#)

```php
esc_html_e( 'The REST API content endpoints were added in WordPress 4.7.', 'your-text-domain' );
```

Alternatively, some people choose to rely on a translation verification mechanism, rather than adding escaping to their code. One example of a verification mechanism is [the editor roles](https://make.wordpress.org/polyglots/handbook/glossary/#project-translation-editor) that the WordPress Polyglots team uses for [translate.wordpress.org](https://translate.wordpress.org/). This ensures that any translation submitted by an untrusted contributor has been verified by a trusted editor before being accepted.

### [Use Placeholders for URLs](https://developer.wordpress.org/plugins/internationalization/security/\#use-placeholders-for-urls)

Don’t include URLs in internationalized strings, because a malicious translator could change them to point to a different URL. Instead, use placeholders for [printf()](http://php.net/manual/en/function.printf.php) or [sprintf()](http://us3.php.net/manual/en/function.sprintf.php).

Insecure:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/security/#)

```php
_e(
	'Please <a href="https://login.wordpress.org/register"> register for a WordPress.org account</a>.',
	'your-text-domain'
);
```

Secure:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/security/#)

```php
printf(
	esc_html__( 'Please %1$s register for a WordPress.org account %2$s.', 'your-text-domain' ),
	'<a href="https://login.wordpress.org/register">',
	'</a>'
);
```

### [Compile Your Own .mo Binaries](https://developer.wordpress.org/plugins/internationalization/security/\#compile-your-own-mo-binaries)

Often translators will send the compiled .mo file along with the plaintext .po file, but you should discard their .mo file and compile your own, because you have no way of knowing whether or not it was compiled from the corresponding .po file, or a different one. If it was compiled against a different one, then it could contain spam and other malicious strings without your knowledge.

Using PoEdit to generate the binary will override the headers in the .po file, so instead it’s better to compile it from the command line:

``
[Copy](https://developer.wordpress.org/plugins/internationalization/security/#)

```bash
msgfmt -cv -o /path/to/output.mo /path/to/input.po
```

First published

April 9, 2015

Last updated

November 17, 2022

[PreviousHow to Internationalize Your PluginPrevious: How to Internationalize Your Plugin](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/)

[NextLocalizationNext: Localization](https://developer.wordpress.org/plugins/internationalization/localization/)

Notifications