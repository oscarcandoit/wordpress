---
url: https://www.php.net/manual/en/ini.core.php
scraped_at: 2025-10-20T02:48:07.581Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Description of core php.ini directives [¶](https://www.php.net/manual/en/ini.core.php\#ini.core)

This list includes the core php.ini directives you can set to
configure your PHP setup. Directives handled by extensions are listed
and detailed at the extension documentation pages respectively;
Information on the session directives for example can be found at the
[sessions page](https://www.php.net/manual/en/session.configuration.php).


> **Note**:
>
>
> The defaults listed here are used when php.ini is not loaded; the values for the production and development php.ini may vary.

## Language Options [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.language-options)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [short\_open\_tag](https://www.php.net/manual/en/ini.core.php#ini.short-open-tag) | "1" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [precision](https://www.php.net/manual/en/ini.core.php#ini.precision) | "14" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [serialize\_precision](https://www.php.net/manual/en/ini.core.php#ini.serialize-precision) | "-1" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** | Prior to PHP 7.1.0, the default value was 17. |
| [disable\_functions](https://www.php.net/manual/en/ini.core.php#ini.disable-functions) | "" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** only |  |
| [disable\_classes](https://www.php.net/manual/en/ini.core.php#ini.disable-classes) | "" | php.ini only |  |
| [exit\_on\_timeout](https://www.php.net/manual/en/ini.core.php#ini.exit-on-timeout) | "" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [expose\_php](https://www.php.net/manual/en/ini.core.php#ini.expose-php) | "1" | php.ini only |  |
| [hard\_timeout](https://www.php.net/manual/en/ini.core.php#ini.hard-timeout) | "2" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** | Available as of PHP 7.1.0. |
| [zend.exception\_ignore\_args](https://www.php.net/manual/en/ini.core.php#ini.zend.exception-ignore-args) | "0" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** | Available as of PHP 7.4.0 |
| [zend.multibyte](https://www.php.net/manual/en/ini.core.php#ini.zend.multibyte) | "0" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [zend.script\_encoding](https://www.php.net/manual/en/ini.core.php#ini.zend.script-encoding) | NULL | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [zend.detect\_unicode](https://www.php.net/manual/en/ini.core.php#ini.zend.detect-unicode) | NULL | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [zend.signal\_check](https://www.php.net/manual/en/ini.core.php#ini.zend.signal-check) | "0" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [zend.assertions](https://www.php.net/manual/en/ini.core.php#ini.zend.assertions) | "1" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** with restrictions |  |
| [zend.exception\_string\_param\_max\_len](https://www.php.net/manual/en/ini.core.php#ini.zend.exception-string-param-max-len) | "15" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** | Available as of PHP 8.0.0. |

**Language and Misc Configuration Options**

Here's a short explanation of
the configuration directives.

`short_open_tag` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Tells PHP whether the short form ( **`<? ?>`**)
of PHP's open tag should be allowed. If you want to use PHP in
combination with XML, you can disable this option in order to
use **`<?xml ?>`** inline. Otherwise, you
can print it with PHP, for example: **`<?php echo '<?xml**
**version="1.0"?>'; ?>`**. Also, if disabled, you must use the
long form of the PHP open tag ( **`<?php ?>`**).


> **Note**:
>
>
> This directive does not affect the shorthand
> **`<?=`**, which is always available.

`precision` [int](https://www.php.net/manual/en/language.types.integer.php)
The number of significant digits displayed in floating point numbers.
`-1` means that an enhanced algorithm for rounding
such numbers will be used.
`serialize_precision` [int](https://www.php.net/manual/en/language.types.integer.php)
The number of significant digits stored while serializing floating point numbers.
`-1` means that an enhanced algorithm for rounding
such numbers will be used.
`expose_php` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Exposes to the world that PHP is installed on the server, which includes the
PHP version within the HTTP header (e.g., X-Powered-By: PHP/5.3.7).


`disable_functions` [string](https://www.php.net/manual/en/language.types.string.php)
This directive allows certain functions to be disabled.
It takes a comma-delimited list of function names.
As of PHP 8.0.0, disabling a function removes its definition,
allowing userland to redefine it.
Prior to PHP 8.0.0, disabling a function just prevented the function
from being invoked.

Only [internal functions](https://www.php.net/manual/en/functions.internal.php) can
be disabled using this directive.
[User-defined functions](https://www.php.net/manual/en/functions.user-defined.php)
are unaffected.

This directive must be set in php.ini.
It cannot be set in httpd.conf.
`disable_classes` [string](https://www.php.net/manual/en/language.types.string.php)

This directive allows certain classes to be disabled.
It takes a comma-delimited list of class names.
Disabling a class just prevents the class's instantiation.


Only internal classes can be disabled using this directive.
User-defined classes are unaffected.


This directive must be set in php.ini.
It cannot be set in httpd.conf.
`zend.assertions` [int](https://www.php.net/manual/en/language.types.integer.php)
When set to `1`, assertion code will be generated and
executed (development mode). When set to `0`,
assertion code will be generated but it will be skipped (not executed)
at runtime. When set to `-1`, assertion code will not
be generated, making the assertions zero-cost (production mode).


> **Note**:
>
>
> If a process is started in production mode, [zend.assertions](https://www.php.net/manual/en/ini.core.php#ini.zend.assertions)
> cannot be changed at runtime, since the code for assertions was not generated.
>
>
> If a process is started in development mode, [zend.assertions](https://www.php.net/manual/en/ini.core.php#ini.zend.assertions)
> cannot be set to `-1` at runtime.

`zend.exception_string_param_max_len` [int](https://www.php.net/manual/en/language.types.integer.php)
The maximum length of string function arguments in stringified stack traces.
Must range between `"0"` and `"1000000"`.
`hard_timeout` [int](https://www.php.net/manual/en/language.types.integer.php)

When the timeout set in [max\_execution\_time](https://www.php.net/manual/en/info.configuration.php#ini.max-execution-time)
has been hit, the PHP runtime will tear down resources gracefully. If
something gets stuck while this happens, the hard timeout will tick
for the set amount of seconds. When the hard timeout is hit, PHP will
exit ungracefully. When set to 0, the hard timeout will never activate.


When PHP stops from a hard timeout, it will look something like this:


```
Fatal error: Maximum execution time of 30+2 seconds exceeded (terminated) in Unknown on line 0

```

`zend.exception_ignore_args` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Excludes arguments from stack traces generated from exceptions.


`zend.multibyte` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Enables parsing of source files in multibyte encodings. Enabling zend.multibyte
is required to use character encodings like SJIS, BIG5, etc that contain special
characters in multibyte string data. ISO-8859-1 compatible encodings like UTF-8,
EUC, etc do not require this option.


Enabling zend.multibyte requires the mbstring extension to be available.


`zend.script_encoding` [string](https://www.php.net/manual/en/language.types.string.php)

This value will be used unless a
[declare(encoding=...)](https://www.php.net/manual/en/control-structures.declare.php#control-structures.declare.encoding)
directive appears at the top of the script. When ISO-8859-1 incompatible encoding
is used, both zend.multibyte and zend.script\_encoding must be used.


Literal strings will be transliterated from zend.script\_encoding to
mbstring.internal\_encoding, as if
[mb\_convert\_encoding()](https://www.php.net/manual/en/function.mb-convert-encoding.php) would have been called.


`zend.detect_unicode` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Check for BOM (Byte Order Mark) and see if the file contains valid
multibyte characters.
This detection is performed before processing of
[\_\_halt\_compiler()](https://www.php.net/manual/en/function.halt-compiler.php).
Available only in Zend Multibyte mode.


`zend.signal_check` [bool](https://www.php.net/manual/en/language.types.boolean.php)

To check for replaced signal handlers on shutdown.


`exit_on_timeout` [bool](https://www.php.net/manual/en/language.types.boolean.php)

This is an Apache1 mod\_php-only directive that forces an Apache child to exit if a PHP execution timeout occurred.
Such a timeout causes an internal longjmp() call in Apache1 which can leave some extensions in an inconsistent
state. By terminating the process any outstanding locks or memory will be cleaned up.


## Resource Limits [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.resource-limits)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [memory\_limit](https://www.php.net/manual/en/ini.core.php#ini.memory-limit) | "128M" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |

**Resource Limits**

Here's a short explanation of
the configuration directives.

`memory_limit` [int](https://www.php.net/manual/en/language.types.integer.php)

This sets the maximum amount of memory in bytes that a script
is allowed to allocate. This helps prevent poorly written
scripts for eating up all available memory on a server. Note that
to have no memory limit, set this directive to `-1`.


When an [int](https://www.php.net/manual/en/language.types.integer.php) is used, the
value is measured in bytes. Shorthand notation, as described
in [this FAQ](https://www.php.net/manual/en/faq.using.php#faq.using.shorthandbytes), may also be used.

See also: [max\_execution\_time](https://www.php.net/manual/en/info.configuration.php#ini.max-execution-time).


## Performance Tuning [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.performance)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [realpath\_cache\_size](https://www.php.net/manual/en/ini.core.php#ini.realpath-cache-size) | "4M" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** | Prior to PHP 7.0.16 and 7.1.2, the default was `"16K"` |
| [realpath\_cache\_ttl](https://www.php.net/manual/en/ini.core.php#ini.realpath-cache-ttl) | "120" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |

**Performance Tuning**

> **Note**:
>
>
> Using [open\_basedir](https://www.php.net/manual/en/ini.core.php#ini.open-basedir) will
> _disable_ the realpath cache.

Here's a short explanation of
the configuration directives.

`realpath_cache_size` [int](https://www.php.net/manual/en/language.types.integer.php)

Determines the size of the realpath cache to be used by PHP. This
value should be increased on systems where PHP opens many files, to
reflect the quantity of the file operations performed.


The size represents the total number of bytes in the path strings
stored, plus the size of the data associated with the cache entry. This
means that in order to store longer paths in the cache, the cache size
must be larger. This value does not directly control the number of
distinct paths that can be cached.


The size required for the cache entry data is system dependent.


`realpath_cache_ttl` [int](https://www.php.net/manual/en/language.types.integer.php)

Duration of time (in seconds) for which to cache realpath information
for a given file or directory. For systems with rarely changing files,
consider increasing the value.


## Data Handling [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.data-handling)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [arg\_separator.output](https://www.php.net/manual/en/ini.core.php#ini.arg-separator.output) | "&" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [arg\_separator.input](https://www.php.net/manual/en/ini.core.php#ini.arg-separator.input) | "&" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [variables\_order](https://www.php.net/manual/en/ini.core.php#ini.variables-order) | "EGPCS" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [request\_order](https://www.php.net/manual/en/ini.core.php#ini.request-order) | "" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [auto\_globals\_jit](https://www.php.net/manual/en/ini.core.php#ini.auto-globals-jit) | "1" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [register\_argc\_argv](https://www.php.net/manual/en/ini.core.php#ini.register-argc-argv) | "1" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [enable\_post\_data\_reading](https://www.php.net/manual/en/ini.core.php#ini.enable-post-data-reading) | "1" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [post\_max\_size](https://www.php.net/manual/en/ini.core.php#ini.post-max-size) | "8M" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [auto\_prepend\_file](https://www.php.net/manual/en/ini.core.php#ini.auto-prepend-file) | NULL | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [auto\_append\_file](https://www.php.net/manual/en/ini.core.php#ini.auto-append-file) | NULL | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [default\_mimetype](https://www.php.net/manual/en/ini.core.php#ini.default-mimetype) | "text/html" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [default\_charset](https://www.php.net/manual/en/ini.core.php#ini.default-charset) | "UTF-8" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [input\_encoding](https://www.php.net/manual/en/ini.core.php#ini.input-encoding) | "" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [output\_encoding](https://www.php.net/manual/en/ini.core.php#ini.output-encoding) | "" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [internal\_encoding](https://www.php.net/manual/en/ini.core.php#ini.internal-encoding) | "" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |

**Data Handling Configuration Options**

Here's a short explanation of
the configuration directives.

`arg_separator.output` [string](https://www.php.net/manual/en/language.types.string.php)

The separator used in PHP generated URLs to separate arguments.


`arg_separator.input` [string](https://www.php.net/manual/en/language.types.string.php)

List of separator(s) used by PHP to parse input URLs into variables.


> **Note**:
>
>
> Every character in this directive is considered as separator!

`variables_order` [string](https://www.php.net/manual/en/language.types.string.php)

Sets the order of the EGPCS ( `E` nvironment,
`G` et, `P` ost,
`C` ookie, and `S` erver) variable
parsing. For example, if variables\_order
is set to `"SP"` then PHP will create the
[superglobals](https://www.php.net/manual/en/language.variables.predefined.php) [$\_SERVER](https://www.php.net/manual/en/reserved.variables.server.php) and
[$\_POST](https://www.php.net/manual/en/reserved.variables.post.php), but not create
[$\_ENV](https://www.php.net/manual/en/reserved.variables.environment.php), [$\_GET](https://www.php.net/manual/en/reserved.variables.get.php), and
[$\_COOKIE](https://www.php.net/manual/en/reserved.variables.cookies.php). Setting to "" means no
[superglobals](https://www.php.net/manual/en/language.variables.predefined.php) will be set.


**Warning**

In both the CGI and FastCGI SAPIs,
[$\_SERVER](https://www.php.net/manual/en/reserved.variables.server.php) is
also populated by values from the environment; `S`
is always equivalent to `ES` regardless of the
placement of `E` elsewhere in this directive.


> **Note**:
>
>
> The content and order of
> [$\_REQUEST](https://www.php.net/manual/en/reserved.variables.request.php) is also
> affected by this directive.

`request_order` [string](https://www.php.net/manual/en/language.types.string.php)

This directive describes the order in which PHP registers GET, POST
and Cookie variables into the \_REQUEST array. Registration is done
from left to right, newer values override older values.


If this directive is not set, [variables\_order](https://www.php.net/manual/en/ini.core.php#ini.variables-order) is used for
[$\_REQUEST](https://www.php.net/manual/en/reserved.variables.request.php) contents.


Note that the default distribution php.ini files does not contain
the `'C'` for cookies, due to security concerns.


`auto_globals_jit` [bool](https://www.php.net/manual/en/language.types.boolean.php)

When enabled, the SERVER, REQUEST, and ENV variables are created when they're
first used (Just In Time) instead of when the script starts. If these
variables are not used within a script, having this directive on will
result in a performance gain.


**Warning**

Usage of SERVER, REQUEST, and ENV variables is checked during the compile time
so using them through e.g. [variable variables](https://www.php.net/manual/en/language.variables.variable.php) will
not cause their initialization.


`register_argc_argv` [bool](https://www.php.net/manual/en/language.types.boolean.php)
Tells PHP whether to declare the argv & argc variables
(that would contain the GET information).

See also [command line](https://www.php.net/manual/en/features.commandline.php).
`enable_post_data_reading` [bool](https://www.php.net/manual/en/language.types.boolean.php)
Disabling this option causes [$\_POST](https://www.php.net/manual/en/reserved.variables.post.php) and
[$\_FILES](https://www.php.net/manual/en/reserved.variables.files.php) _not_ to be populated.
The only way to read postdata will then be through the
[php://input](https://www.php.net/manual/en/wrappers.php.php) stream wrapper.
This can be useful to proxy requests or to process
the POST data in a memory efficient fashion.
`post_max_size` [int](https://www.php.net/manual/en/language.types.integer.php)
Sets max size of post data allowed. This setting also affects
file upload. To upload large files, this value must be larger
than [upload\_max\_filesize](https://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize).

Generally speaking,
[memory\_limit](https://www.php.net/manual/en/ini.core.php#ini.memory-limit) should be
larger than `post_max_size`.
When an [int](https://www.php.net/manual/en/language.types.integer.php) is used, the
value is measured in bytes. Shorthand notation, as described
in [this FAQ](https://www.php.net/manual/en/faq.using.php#faq.using.shorthandbytes), may also be used.

If the size of post data is greater than post\_max\_size, the
[$\_POST](https://www.php.net/manual/en/reserved.variables.post.php) and [$\_FILES](https://www.php.net/manual/en/reserved.variables.files.php) [superglobals](https://www.php.net/manual/en/language.variables.superglobals.php)
are empty. This can be tracked in various ways, e.g. by passing the
[$\_GET](https://www.php.net/manual/en/reserved.variables.get.php) variable to the script processing the data,
i.e. `<form action="edit.php?processed=1">`,
and then checking if [$\_GET\['processed'\]](https://www.php.net/manual/en/reserved.variables.get.php) is set.


> **Note**:
>
>
> PHP allows shortcuts for byte values, including K (kilo), M (mega)
> and G (giga). PHP will do the conversions automatically if you
> use any of these. Be careful not to exceed the 32 bit signed integer
> limit (if you're using 32bit versions) as it will cause your script
> to fail.

| Version | Description |
| --- | --- |
| 5.3.4 | `post_max_size` = 0 will not disable the limit when the content<br> type is application/x-www-form-urlencoded or is not registered with PHP. |
| 5.3.2 , 5.2.12 | Allow unlimited post size by setting `post_max_size` to 0. |

**Changelog for `post_max_size`**

`auto_prepend_file` [string](https://www.php.net/manual/en/language.types.string.php)

Specifies the name of a file that is automatically parsed
before the main file. The file is included as if it was
called with the [require](https://www.php.net/manual/en/function.require.php) function, so
[include\_path](https://www.php.net/manual/en/ini.core.php#ini.include-path) is used.

The special value `none`
disables auto-prepending.


`auto_append_file` [string](https://www.php.net/manual/en/language.types.string.php)

Specifies the name of a file that is automatically parsed
after the main file. The file is included as if it was
called with the [require](https://www.php.net/manual/en/function.require.php) function, so
[include\_path](https://www.php.net/manual/en/ini.core.php#ini.include-path) is used.

The special value `none`
disables auto-appending.


> **Note**:
>
> If the script is terminated with [exit()](https://www.php.net/manual/en/function.exit.php),
> auto-append will _not_ occur.

`default_mimetype` [string](https://www.php.net/manual/en/language.types.string.php)

By default, PHP will output a media type using the Content-Type header.
To disable this, simply set it to be empty.


PHP's built-in default media type is set to text/html.


`default_charset` [string](https://www.php.net/manual/en/language.types.string.php)

"UTF-8" is the default value and its value is used
as the default character encoding for
[htmlentities()](https://www.php.net/manual/en/function.htmlentities.php),
[html\_entity\_decode()](https://www.php.net/manual/en/function.html-entity-decode.php) and
[htmlspecialchars()](https://www.php.net/manual/en/function.htmlspecialchars.php) if the
`encoding` parameter is omitted. The value of
`default_charset` will also be used to set the
default character set for [iconv](https://www.php.net/manual/en/book.iconv.php)
functions if the
[`iconv.input_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.input-encoding),
[`iconv.output_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.output-encoding) and
[`iconv.internal_encoding`](https://www.php.net/manual/en/iconv.configuration.php#ini.iconv.internal-encoding)
configuration options are unset, and for
[mbstring](https://www.php.net/manual/en/book.mbstring.php) functions if the
[`mbstring.http_input`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.http-input) [`mbstring.http_output`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.http-output) [`mbstring.internal_encoding`](https://www.php.net/manual/en/mbstring.configuration.php#ini.mbstring.internal-encoding)
configuration option is unset.


All versions of PHP will use this value as the charset within the
default Content-Type header sent by PHP if the header isn't overridden
by a call to [header()](https://www.php.net/manual/en/function.header.php).


Setting `default_charset` to an empty value is
not recommended.


`input_encoding` [string](https://www.php.net/manual/en/language.types.string.php)

This setting is used for multibyte modules
such as mbstring and iconv. Default is empty.


`output_encoding` [string](https://www.php.net/manual/en/language.types.string.php)

This setting is used for multibyte modules
such as mbstring and iconv. Default is empty.


`internal_encoding` [string](https://www.php.net/manual/en/language.types.string.php)

This setting is used for multibyte modules
such as mbstring and iconv. Default is empty. If empty,
[default\_charset](https://www.php.net/manual/en/ini.core.php#ini.default-charset) is used.


## Paths and Directories [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.path-directory)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [include\_path](https://www.php.net/manual/en/ini.core.php#ini.include-path) | ".;/path/to/php/pear" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [open\_basedir](https://www.php.net/manual/en/ini.core.php#ini.open-basedir) | NULL | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [doc\_root](https://www.php.net/manual/en/ini.core.php#ini.doc-root) | NULL | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [user\_dir](https://www.php.net/manual/en/ini.core.php#ini.user-dir) | NULL | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [user\_ini.cache\_ttl](https://www.php.net/manual/en/ini.core.php#ini.user-ini.cache-ttl) | "300" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [user\_ini.filename](https://www.php.net/manual/en/ini.core.php#ini.user-ini.filename) | ".user.ini" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [extension\_dir](https://www.php.net/manual/en/ini.core.php#ini.extension-dir) | "/path/to/php" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [extension](https://www.php.net/manual/en/ini.core.php#ini.extension) | NULL | php.ini only |  |
| [zend\_extension](https://www.php.net/manual/en/ini.core.php#ini.zend-extension) | NULL | php.ini only |  |
| [cgi.check\_shebang\_line](https://www.php.net/manual/en/ini.core.php#ini.cgi.check-shebang-line) | "1" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.discard\_path](https://www.php.net/manual/en/ini.core.php#ini.cgi.discard-path) | "0" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.fix\_pathinfo](https://www.php.net/manual/en/ini.core.php#ini.cgi.fix-pathinfo) | "1" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.force\_redirect](https://www.php.net/manual/en/ini.core.php#ini.cgi.force-redirect) | "1" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.nph](https://www.php.net/manual/en/ini.core.php#ini.cgi.nph) | "0" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.redirect\_status\_env](https://www.php.net/manual/en/ini.core.php#ini.cgi.redirect-status-env) | NULL | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [cgi.rfc2616\_headers](https://www.php.net/manual/en/ini.core.php#ini.cgi.rfc2616-headers) | "0" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |
| [fastcgi.impersonate](https://www.php.net/manual/en/ini.core.php#ini.fastcgi.impersonate) | "0" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [fastcgi.logging](https://www.php.net/manual/en/ini.core.php#ini.fastcgi.logging) | "1" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |

**Paths and Directories Configuration Options**

Here's a short explanation of
the configuration directives.

`include_path` [string](https://www.php.net/manual/en/language.types.string.php)

Specifies a list of directories where the
[require](https://www.php.net/manual/en/function.require.php), [include](https://www.php.net/manual/en/function.include.php),
[fopen()](https://www.php.net/manual/en/function.fopen.php), [file()](https://www.php.net/manual/en/function.file.php),
[readfile()](https://www.php.net/manual/en/function.readfile.php) and [file\_get\_contents()](https://www.php.net/manual/en/function.file-get-contents.php)
functions look for files. The format is like the system's
PATH environment variable: a list of directories
separated with a colon in Unix or semicolon in Windows.


PHP considers each entry in the include path separately when looking for
files to include. It will check the first path, and if it doesn't find
it, check the next path, until it either locates the included file or
returns with an
**`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`**
or an **`[E\_ERROR](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-error)`**.
You may modify or set your include path at runtime using
[set\_include\_path()](https://www.php.net/manual/en/function.set-include-path.php).


**Example #1 Unix include\_path**

```
include_path=".:/php/includes"
```

**Example #2 Windows include\_path**

```
include_path=".;c:\php\includes"
```

Using a `.` in the include path allows for
relative includes as it means the current directory. However,
it is more efficient to explicitly use `include
        './file'` than having PHP always check the current
directory for every include.


> **Note**:
>
>
> `ENV` variables are also accessible in .ini files.
> As such it is possible to reference the home directory using
> `${LOGIN}` and `${USER}`.
>
>
> Environment variables may vary between Server APIs as those environments
> may be different.

**Example #3 Unix include\_path using ${USER} env variable**

```
include_path = ".:${USER}/pear/php"
```

`open_basedir` [string](https://www.php.net/manual/en/language.types.string.php)

Limit the files that can be accessed by PHP to the specified
directory-tree, including the file itself.


When a script tries to access the filesystem, for example using
[include](https://www.php.net/manual/en/function.include.php), or [fopen()](https://www.php.net/manual/en/function.fopen.php), the location of the file
is checked.
When the file is outside the specified directory-tree, PHP will refuse to access it.
All symbolic links are resolved, so it's not possible to avoid this restriction
with a symlink. If the file doesn't exist then the symlink couldn't be
resolved and the filename is compared to (a resolved) **open\_basedir**.


**open\_basedir** can affect more than just filesystem functions; for example
if `MySQL` is configured to use `mysqlnd` drivers,
`LOAD DATA INFILE` will be affected by **open\_basedir**.
Much of the extended functionality of PHP uses `open_basedir` in this way.


The special value `.`
indicates that the working directory of the script will be used as the
base-directory. This is, however, a little dangerous as the working directory
of the script can easily be changed with [chdir()](https://www.php.net/manual/en/function.chdir.php).


In httpd.conf, **open\_basedir** can be turned off
(e.g. for some virtual hosts)
[the same way](https://www.php.net/manual/en/configuration.changes.php#configuration.changes.apache) as
any other configuration directive with " `php_admin_value open_basedir
        none`".


Under Windows, separate the directories with a semicolon. On all
other systems, separate the directories with a colon. As an Apache
module, **open\_basedir** paths from parent directories are now
automatically inherited.


The restriction specified with **open\_basedir** is a
directory name, not a prefix.


The default is to allow all files to be opened.


> **Note**:
>
> open\_basedir can be tightened at run-time. This means
> that if open\_basedir is set to `/www/` in php.ini
> a script can tighten the configuration to
> `/www/tmp/` at run-time with
> [ini\_set()](https://www.php.net/manual/en/function.ini-set.php). When listing several directories, you
> can use the **`[PATH\_SEPARATOR](https://www.php.net/manual/en/dir.constants.php#constant.path-separator)`** constant as a separator
> regardless of the operating system.
>
> As of PHP 8.3.0, **open\_basedir** no longer accepts a
> paths containing the parent directory ( `..`) when
> set at runtime using [ini\_set()](https://www.php.net/manual/en/function.ini-set.php).

> **Note**:
>
>
> Using open\_basedir will set [realpath\_cache\_size](https://www.php.net/manual/en/ini.core.php#ini.realpath-cache-size)
> to `0` and thus _disable_ the realpath cache.

**Caution**

`open_basedir` is just an extra safety net, that is in no way
comprehensive, and can therefore not be relied upon when security is needed.


`doc_root` [string](https://www.php.net/manual/en/language.types.string.php)

PHP's "root directory" on the server. Only used if
non-empty.
If PHP was not compiled with FORCE\_REDIRECT, you _should_ set doc\_root if you are running PHP as a CGI under any web
server (other than IIS). The alternative is to use the
[cgi.force\_redirect](https://www.php.net/manual/en/ini.core.php#ini.cgi.force-redirect) configuration below.


`user_ini.cache_ttl` [int](https://www.php.net/manual/en/language.types.integer.php)

`user_ini.filename` [string](https://www.php.net/manual/en/language.types.string.php)

`user_dir` [string](https://www.php.net/manual/en/language.types.string.php)

The base name of the directory used on a user's home directory for PHP
files, for example public\_html
.


`extension_dir` [string](https://www.php.net/manual/en/language.types.string.php)

In what directory PHP should look for dynamically loadable
extensions. It is recommended to specify an absolute path. See also: [enable\_dl](https://www.php.net/manual/en/info.configuration.php#ini.enable-dl),
and [dl()](https://www.php.net/manual/en/function.dl.php).


`extension` [string](https://www.php.net/manual/en/language.types.string.php)

Which dynamically loadable extensions to load when PHP starts up.


`zend_extension` [string](https://www.php.net/manual/en/language.types.string.php)

Name of dynamically loadable Zend extension (for example
XDebug) to load when PHP starts up.


`cgi.check_shebang_line` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Controls whether CGI PHP checks for line starting
with `#!` (shebang) at the top of the running script.
This line might be needed if the script support running both as
stand-alone script and via PHP CGI. PHP in
CGI mode skips this line and ignores its content if
this directive is turned on.


`cgi.discard_path` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If this is enabled, the PHP CGI binary can safely be placed outside of
the web tree and people will not be able to circumvent .htaccess security.


`cgi.fix_pathinfo` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Provides _real_ `PATH_INFO`/
`PATH_TRANSLATED` support for CGI.
PHP's previous behaviour was to set `PATH_TRANSLATED`
to `SCRIPT_FILENAME`, and to not grok what `
        PATH_INFO` is. For more information on
`PATH_INFO`, see the CGI specs.
Setting this to `1` will cause PHP
CGI to fix its paths to conform to the spec. A
setting of zero causes PHP to behave as before. It is turned on by
default. You should fix your scripts to use
`SCRIPT_FILENAME` rather than
`PATH_TRANSLATED`.


`cgi.force_redirect` [bool](https://www.php.net/manual/en/language.types.boolean.php)

cgi.force\_redirect is necessary to provide security running PHP as a
CGI under most web servers. Left undefined, PHP
turns this on by default. You can turn it off _at your own_
_risk_.


> **Note**:
>
>
> Windows Users: When using IIS this option _must_
> be turned off. For OmniHTTPD or Xitami the same applies.

`cgi.nph` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If cgi.nph is enabled it will force cgi to always sent Status: 200 with
every request.


`cgi.redirect_status_env` [string](https://www.php.net/manual/en/language.types.string.php)

If cgi.force\_redirect is turned on, and you are not running under
Apache or Netscape (iPlanet) web servers, you _may_
need to set an environment variable name that PHP will look for to
know it is OK to continue execution.


> **Note**:
>
>
> Setting this variable _may_ cause security issues,
> _know what you are doing first_.

`cgi.rfc2616_headers` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Tells PHP what type of headers to use when sending HTTP response
code. If it is disabled, PHP sends a [» RFC 3875](https://datatracker.ietf.org/doc/html/rfc3875)
"Status:" header that is supported by Apache and other web servers. When this option
is enabled, PHP will send [» RFC 2616](https://datatracker.ietf.org/doc/html/rfc2616) compliant
headers.


If this option is enabled, and you are running PHP in a CGI environment (e.g. PHP-FPM)
you should not use standard RFC 2616 style HTTP status response headers, you should
instead use their RFC 3875 equivalent e.g. instead of header("HTTP/1.0 404 Not found");
you should use header("Status: 404 Not Found");


Leave it disabled unless you know what you're doing.


`fastcgi.impersonate` [bool](https://www.php.net/manual/en/language.types.boolean.php)

FastCGI under IIS (on WINNT based OS) supports the ability to impersonate
security tokens of the calling client. This allows IIS to define the
security context that the request runs under. mod\_fastcgi under Apache
does not currently support this feature (03/17/2002)
Enable if running under IIS. Default is disabled.


`fastcgi.logging` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Turns on SAPI logging when using FastCGI. Default is
to enable logging.


## File Uploads [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.file-uploads)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [file\_uploads](https://www.php.net/manual/en/ini.core.php#ini.file-uploads) | "1" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [upload\_tmp\_dir](https://www.php.net/manual/en/ini.core.php#ini.upload-tmp-dir) | NULL | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** |  |
| [max\_input\_nesting\_level](https://www.php.net/manual/en/info.configuration.php#ini.max-input-nesting-level) | 64 | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [max\_input\_vars](https://www.php.net/manual/en/info.configuration.php#ini.max-input-vars) | 1000 | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [upload\_max\_filesize](https://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize) | "2M" | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |
| [max\_file\_uploads](https://www.php.net/manual/en/ini.core.php#ini.max-file-uploads) | 20 | **`[INI\_PERDIR](https://www.php.net/manual/en/info.constants.php#constant.ini-perdir)`** |  |

**File Uploads Configuration Options**

Here's a short explanation of
the configuration directives.

`file_uploads` [bool](https://www.php.net/manual/en/language.types.boolean.php)

Whether or not to allow HTTP
[file uploads](https://www.php.net/manual/en/features.file-upload.php). See also the
[upload\_max\_filesize](https://www.php.net/manual/en/ini.core.php#ini.upload-max-filesize),
[upload\_tmp\_dir](https://www.php.net/manual/en/ini.core.php#ini.upload-tmp-dir), and
[post\_max\_size](https://www.php.net/manual/en/ini.core.php#ini.post-max-size) directives.


`upload_tmp_dir` [string](https://www.php.net/manual/en/language.types.string.php)

The temporary directory used for storing files when doing
file upload. Must be writable by whatever user PHP
is running as. If not specified PHP will use the system's default.


If the directory specified here is not writable, PHP falls back to
the system default temporary directory. If
[open\_basedir](https://www.php.net/manual/en/ini.core.php#ini.open-basedir) is on, then
the system default directory must be allowed for an upload to
succeed.


`upload_max_filesize` [int](https://www.php.net/manual/en/language.types.integer.php)

The maximum size of an uploaded file.


[post\_max\_size](https://www.php.net/manual/en/ini.core.php#ini.post-max-size) must be larger than this value.


When an [int](https://www.php.net/manual/en/language.types.integer.php) is used, the
value is measured in bytes. Shorthand notation, as described
in [this FAQ](https://www.php.net/manual/en/faq.using.php#faq.using.shorthandbytes), may also be used.
`max_file_uploads` [int](https://www.php.net/manual/en/language.types.integer.php)

The maximum number of files allowed to be uploaded simultaneously.
Upload fields left blank on submission do not
count towards this limit.


## General SQL [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.sql-general)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [sql.safe\_mode](https://www.php.net/manual/en/ini.core.php#ini.sql.safe-mode) | "0" | **`[INI\_SYSTEM](https://www.php.net/manual/en/info.constants.php#constant.ini-system)`** | Removed as of PHP 7.2.0 |

**General SQL Configuration Options**

Here's a short explanation of
the configuration directives.

`sql.safe_mode` [bool](https://www.php.net/manual/en/language.types.boolean.php)

If turned on, database connection functions that specify default values
will use those values in place of any user-supplied arguments. For details
on the default values, see the documentation for the relevant connection
functions.


**Warning**

This feature has been _REMOVED_ as of PHP 7.2.0.


## Windows Specific [¶](https://www.php.net/manual/en/ini.core.php\#ini.sect.windows)

| Name | Default | Changeable | Changelog |
| --- | --- | --- | --- |
| [windows.show\_crt\_warning](https://www.php.net/manual/en/ini.core.php#ini.windows-show-crt-warning) | "0" | **`[INI\_ALL](https://www.php.net/manual/en/info.constants.php#constant.ini-all)`** |  |

**Windows Specific Configuration Options**

Here's a short explanation of
the configuration directives.

`windows.show_crt_warning` [bool](https://www.php.net/manual/en/language.types.boolean.php)

This directive shows the Windows CRT warnings when enabled.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/ini.core.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fini.core%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=ini.core&repo=en&redirect=https://www.php.net/manual/en/ini.core.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=124786&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124786&page=ini.core&vote=down "Vote down!")

17


[**_luisdev_**](https://www.php.net/manual/en/ini.core.php#124786) [¶](https://www.php.net/manual/en/ini.core.php#124786)

**5 years ago**

`[https://haydenjames.io/understanding-php-memory\_limit/](https://haydenjames.io/understanding-php-memory_limit/) explains the memory_limit setting nicely.`

[up](https://www.php.net/manual/vote-note.php?id=125695&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125695&page=ini.core&vote=down "Vote down!")

10


[**_Simone Pellegatta_**](https://www.php.net/manual/en/ini.core.php#125695) [¶](https://www.php.net/manual/en/ini.core.php#125695)

**4 years ago**

`Be careful while using auto_prepend_file.
When the custom exception handler, set by set_exception_handler(), handles an uncaught exception, it interrupts the execution of every script.
If the script with the unhandled exception has been automatically prepended or included by an automatically prepended script, however, the main script will continue running anyway.
This could cause several issues: when we think that throwing an exception would automatically interrupt the current application, a whole chunk of code is going to run anyway.`

[up](https://www.php.net/manual/vote-note.php?id=120054&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120054&page=ini.core&vote=down "Vote down!")

3


[**_fernandobasso dot br at gmail dot com_**](https://www.php.net/manual/en/ini.core.php#120054) [¶](https://www.php.net/manual/en/ini.core.php#120054)

**9 years ago**

``This might help in case someone happens to maintain old applications with a charset other than utf-8.
According to the docs, you can override the default charset if you use `header()`.
Suppose php.ini sets the default_charset to "UTF-8", but you need a legacy charset, like ISO-8859-1.
Still,
<?php header('Content-Type: text/html; Charset=ISO-8859-1'); ?>
would not override the charset, just add it as well and the result
was a response header like (note the two charsets):
    Content-Type:"text/html; Charset=ISO-8859-1;charset=UTF-8"
I found it strange the default one as `charset` with a lowercase `c`
as opposed to my custom charset with an uppercase `C`.
What solved was to _override_ the charset using all lowercase letters
as well for the word “charset”:
<?php header('content-type: text/html; charset=ISO-8859-1'); ?>
Then, the double charset from the response headers disappeared, and only the single, custom charset remained.``

[up](https://www.php.net/manual/vote-note.php?id=124115&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124115&page=ini.core&vote=down "Vote down!")

2


[**_diamondeagle at webmail dot co dot za_**](https://www.php.net/manual/en/ini.core.php#124115) [¶](https://www.php.net/manual/en/ini.core.php#124115)

**6 years ago**

`Note regarding the upload_tmp_dir setting and UNC Paths:
When using PHP on Windows OS and IIS FastCGI, if you need to use a UNC path to a folder on a network drive for the upload_tmp_dir setting then you must use three \ characters at the front of the UNC path.
Windows and PHP use the first slash as an escape character, so if you only use two slashes then it passes a UNC path with just one backslash. That is not valid for UNC paths and you many experience problems when uploading files, such as errors saying that "PHP is missing a temporary folder".
Correct:
upload_tmp_dir = "\\\path\to\your\folder"
Incorrect:
upload_tmp_dir = "\\path\to\your\folder"`

[up](https://www.php.net/manual/vote-note.php?id=66801&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=66801&page=ini.core&vote=down "Vote down!")

3


[**_leo at korfu dot cz_**](https://www.php.net/manual/en/ini.core.php#66801) [¶](https://www.php.net/manual/en/ini.core.php#66801)

**19 years ago**

`"If the size of post data is greater than post_max_size..."
It seems that a more elegant way is comparison between post_max_size and $_SERVER['CONTENT_LENGTH']. Please note that the latter includes not only size of uploaded file plus post data but also multipart sequences. Leo`

[up](https://www.php.net/manual/vote-note.php?id=129570&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129570&page=ini.core&vote=down "Vote down!")

 -1


[**_gcb@_**](https://www.php.net/manual/en/ini.core.php#129570) [¶](https://www.php.net/manual/en/ini.core.php#129570)

**1 year ago**

`you get a misleading error if a directory doesn't exist or the user lacks permission to access it.
open_basedir restriction in effect. File(/tmp/php_session) is not within the allowed path(s): /tmp/php_session`

[up](https://www.php.net/manual/vote-note.php?id=125951&page=ini.core&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125951&page=ini.core&vote=down "Vote down!")

 -3


[**_andre dot wetter at myelco dot ch_**](https://www.php.net/manual/en/ini.core.php#125951) [¶](https://www.php.net/manual/en/ini.core.php#125951)

**4 years ago**

`If you use Microsoft IIS Windows and want to use open_basedir restrictions with multiple dirs you have to set them into single quotes in the main config xml file of IIS (C:\Windows\System32\inetsrv\config\applicationHost.config). Works fine in IIS 10.
Multiple files with single quotes and ; for windows:
"C:\php\php-cgi.exe|-d open_basedir='C:\Windows\Temp\;D:\mywebsite1\'"
Only one dir works fine without single quotes:
"C:\php\php-cgi.exe|-d open_basedir=D:\mywebsite1\"
In my main config xml file of IIS there are 2 nodes to set per website and the definitions have to be equal:
configuration\Location\system.webServer\handlers\add
configuration\system.webServer\fastCgi`

[＋add a note](https://www.php.net/manual/add-note.php?sect=ini.core&repo=en&redirect=https://www.php.net/manual/en/ini.core.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google