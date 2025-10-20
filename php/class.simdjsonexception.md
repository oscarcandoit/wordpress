---
url: https://www.php.net/manual/en/class.simdjsonexception.php
scraped_at: 2025-10-20T02:36:19.146Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SimdJsonException class [¶](https://www.php.net/manual/en/class.simdjsonexception.php\#class.simdjsonexception)

(PECL simdjson >= 2.1.0)

## Introduction [¶](https://www.php.net/manual/en/class.simdjsonexception.php\#simdjsonexception.intro)

Exception thrown if [simdjson\_decode()](https://www.php.net/manual/en/function.simdjson-decode.php),
[simdjson\_key\_count()](https://www.php.net/manual/en/function.simdjson-key-count.php),
[simdjson\_key\_exists()](https://www.php.net/manual/en/function.simdjson-key-exists.php),
or [simdjson\_key\_value()](https://www.php.net/manual/en/function.simdjson-key-value.php).

For possible values see the [simdjson error codes](https://www.php.net/manual/en/simdjson.constants.php) constants.


## Class synopsis [¶](https://www.php.net/manual/en/class.simdjsonexception.php\#simdjsonexception.synopsis)

class **SimdJsonException**extends [RuntimeException](https://www.php.net/manual/en/class.runtimeexception.php)

{

/\\* Inherited properties \*/

protected[string](https://www.php.net/manual/en/language.types.string.php)[$message](https://www.php.net/manual/en/class.exception.php#exception.props.message) = "";

private[string](https://www.php.net/manual/en/language.types.string.php)[$string](https://www.php.net/manual/en/class.exception.php#exception.props.string) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$code](https://www.php.net/manual/en/class.exception.php#exception.props.code);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$file](https://www.php.net/manual/en/class.exception.php#exception.props.file) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$line](https://www.php.net/manual/en/class.exception.php#exception.props.line);

private[array](https://www.php.net/manual/en/language.types.array.php)[$trace](https://www.php.net/manual/en/class.exception.php#exception.props.trace) = \[\];

private?[Throwable](https://www.php.net/manual/en/class.throwable.php)[$previous](https://www.php.net/manual/en/class.exception.php#exception.props.previous) = null;

}

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/simdjson/simdjsonexception.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.simdjsonexception%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.simdjsonexception&repo=en&redirect=https://www.php.net/manual/en/class.simdjsonexception.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google