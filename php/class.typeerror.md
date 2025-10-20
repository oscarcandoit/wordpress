---
url: https://www.php.net/manual/en/class.typeerror.php
scraped_at: 2025-10-20T02:38:52.799Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# TypeError [¶](https://www.php.net/manual/en/class.typeerror.php\#class.typeerror)

(PHP 7, PHP 8)

## Introduction [¶](https://www.php.net/manual/en/class.typeerror.php\#typeerror.intro)

A **TypeError** may be thrown when:


- The value being set for a class property does not match
the property's corresponding declared type.

- The argument type being passed to a function does not match
its corresponding declared parameter type.

- A value being returned from a function does not match the
declared function return type.


## Class synopsis [¶](https://www.php.net/manual/en/class.typeerror.php\#typeerror.synopsis)

class **TypeError** extends [Error](https://www.php.net/manual/en/class.error.php)
{

/\\* Inherited properties \*/

protected[string](https://www.php.net/manual/en/language.types.string.php)[$message](https://www.php.net/manual/en/class.error.php#error.props.message) = "";

private[string](https://www.php.net/manual/en/language.types.string.php)[$string](https://www.php.net/manual/en/class.error.php#error.props.string) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$code](https://www.php.net/manual/en/class.error.php#error.props.code);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$file](https://www.php.net/manual/en/class.error.php#error.props.file) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$line](https://www.php.net/manual/en/class.error.php#error.props.line);

private[array](https://www.php.net/manual/en/language.types.array.php)[$trace](https://www.php.net/manual/en/class.error.php#error.props.trace) = \[\];

private?[Throwable](https://www.php.net/manual/en/class.throwable.php)[$previous](https://www.php.net/manual/en/class.error.php#error.props.previous) = null;

/\\* Inherited methods \*/

public[Error::\_\_construct](https://www.php.net/manual/en/error.construct.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message` = "", [int](https://www.php.net/manual/en/language.types.integer.php) `$code` = 0, [?](https://www.php.net/manual/en/language.types.null.php)[Throwable](https://www.php.net/manual/en/class.throwable.php) `$previous` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**)

finalpublic[Error::getMessage](https://www.php.net/manual/en/error.getmessage.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Error::getPrevious](https://www.php.net/manual/en/error.getprevious.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[Throwable](https://www.php.net/manual/en/class.throwable.php)

finalpublic[Error::getCode](https://www.php.net/manual/en/error.getcode.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Error::getFile](https://www.php.net/manual/en/error.getfile.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Error::getLine](https://www.php.net/manual/en/error.getline.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Error::getTrace](https://www.php.net/manual/en/error.gettrace.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[Error::getTraceAsString](https://www.php.net/manual/en/error.gettraceasstring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[Error::\_\_toString](https://www.php.net/manual/en/error.tostring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

private[Error::\_\_clone](https://www.php.net/manual/en/error.clone.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Changelog [¶](https://www.php.net/manual/en/class.typeerror.php\#typeerror.changelog)

| Version | Description |
| --- | --- |
| 7.1.0 | In strict mode, passing an incorrect number of arguments to a built-in<br> PHP function no longer results in a generic **TypeError**.<br> Instead, a more specific [ArgumentCountError](https://www.php.net/manual/en/class.argumentcounterror.php), which<br> extends **TypeError**, is thrown. |

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/typeerror.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.typeerror%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.typeerror&repo=en&redirect=https://www.php.net/manual/en/class.typeerror.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google