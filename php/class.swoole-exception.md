---
url: https://www.php.net/manual/en/class.swoole-exception.php
scraped_at: 2025-10-20T02:30:58.342Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Swoole\\Exception class [¶](https://www.php.net/manual/en/class.swoole-exception.php\#class.swoole-exception)

(PECL swoole >= 1.9.0)

## Introduction [¶](https://www.php.net/manual/en/class.swoole-exception.php\#swoole-exception.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.swoole-exception.php\#swoole-exception.synopsis)

class **Swoole\\Exception**extends [Exception](https://www.php.net/manual/en/class.exception.php)implements [Throwable](https://www.php.net/manual/en/class.throwable.php) {

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
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/swoole/swoole.exception.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.swoole-exception%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.swoole-exception&repo=en&redirect=https://www.php.net/manual/en/class.swoole-exception.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google