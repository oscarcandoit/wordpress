---
url: https://www.php.net/manual/en/functions.internal.php
scraped_at: 2025-10-20T02:30:48.683Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Internal (built-in) functions [¶](https://www.php.net/manual/en/functions.internal.php\#functions.internal)

PHP comes standard with many functions and constructs. There are also
functions that require specific PHP extensions compiled in, otherwise
fatal "undefined function" errors will appear. For example, to use
[image](https://www.php.net/manual/en/ref.image.php) functions such as
[imagecreatetruecolor()](https://www.php.net/manual/en/function.imagecreatetruecolor.php), PHP must be compiled with
GD support. Or, to use
[mysqli\_connect()](https://www.php.net/manual/en/function.mysqli-connect.php), PHP must be compiled with
[MySQLi](https://www.php.net/manual/en/book.mysqli.php) support. There are many core functions
that are included in every version of PHP, such as the
[string](https://www.php.net/manual/en/ref.strings.php) and
[variable](https://www.php.net/manual/en/ref.var.php) functions. A call
to [phpinfo()](https://www.php.net/manual/en/function.phpinfo.php) or
[get\_loaded\_extensions()](https://www.php.net/manual/en/function.get-loaded-extensions.php) will show which extensions are
loaded into PHP. Also note that many extensions are enabled by default and
that the PHP manual is split up by extension. See the
[configuration](https://www.php.net/manual/en/configuration.php),
[installation](https://www.php.net/manual/en/install.php), and individual
extension chapters, for information on how to set up PHP.


Reading and understanding a function's prototype is explained within the
manual section titled [how to read a\\
function definition](https://www.php.net/manual/en/about.prototypes.php). It's important to realize what a function
returns or if a function works directly on a passed in value. For example,
[str\_replace()](https://www.php.net/manual/en/function.str-replace.php) will return the modified string while
[usort()](https://www.php.net/manual/en/function.usort.php) works on the actual passed in variable
itself. Each manual page also has specific information for each
function like information on function parameters, behavior changes,
return values for both success and failure, and availability information.
Knowing these important (yet often subtle) differences is crucial for
writing correct PHP code.


> **Note**:
>
> If the parameters given to a function are not what it expects, such as
> passing an [array](https://www.php.net/manual/en/language.types.array.php) where a [string](https://www.php.net/manual/en/language.types.string.php) is expected,
> the return value of the function is undefined. In this case it will
> likely return **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** but this is just a convention, and cannot be relied
> upon.
> As of PHP 8.0.0, a [TypeError](https://www.php.net/manual/en/class.typeerror.php) exception is supposed to
> be thrown in this case.

> **Note**:
>
>
> Scalar types for built-in functions are nullable by default in coercive mode.
> As of PHP 8.1.0, passing **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** to an internal function parameter that is not declared nullable
> is discouraged and emits a deprecation notice in coercive mode to align with the behavior of user-defined functions,
> where scalar types need to be marked as nullable explicitly.
>
>
> For example, [strlen()](https://www.php.net/manual/en/function.strlen.php) function expects the parameter `$string`
> to be a non-nullable [string](https://www.php.net/manual/en/language.types.string.php).
> For historical reasons, PHP allows passing **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** for this parameter in coercive mode, and the parameter is
> implicitly cast to [string](https://www.php.net/manual/en/language.types.string.php), resulting in a `""` value.
> In contrast, a [TypeError](https://www.php.net/manual/en/class.typeerror.php) is emitted in strict mode.
>
>
> `<?php
> var_dump(strlen(null));
> // "Deprecated: Passing null to parameter #1 ($string) of type string is deprecated" as of PHP 8.1.0
> // int(0)
> var_dump(str_contains("foobar", null));
> // "Deprecated: Passing null to parameter #2 ($needle) of type string is deprecated" as of PHP 8.1.0
> // bool(true)
> ?>`

### See Also

- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php)
- [the function reference](https://www.php.net/manual/en/funcref.php)
- [get\_extension\_funcs()](https://www.php.net/manual/en/function.get-extension-funcs.php)
- [dl()](https://www.php.net/manual/en/function.dl.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/functions.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunctions.internal%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=functions.internal&repo=en&redirect=https://www.php.net/manual/en/functions.internal.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google