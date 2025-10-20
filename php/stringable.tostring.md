---
url: https://www.php.net/manual/en/stringable.tostring.php
scraped_at: 2025-10-20T03:00:56.818Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Stringable::\_\_toString

(PHP 8)

Stringable::\_\_toString — Gets a string representation of the object

### Description [¶](https://www.php.net/manual/en/stringable.tostring.php\#refsect1-stringable.tostring-description)

public**Stringable::\_\_toString**(): [string](https://www.php.net/manual/en/language.types.string.php)

### Parameters [¶](https://www.php.net/manual/en/stringable.tostring.php\#refsect1-stringable.tostring-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/stringable.tostring.php\#refsect1-stringable.tostring-returnvalues)

Returns the [string](https://www.php.net/manual/en/language.types.string.php) representation of the object.


### See Also [¶](https://www.php.net/manual/en/stringable.tostring.php\#refsect1-stringable.tostring-seealso)

- [\_\_toString()](https://www.php.net/manual/en/language.oop5.magic.php#object.tostring)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/stringable/tostring.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fstringable.tostring%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=stringable.tostring&repo=en&redirect=https://www.php.net/manual/en/stringable.tostring.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=129691&page=stringable.tostring&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129691&page=stringable.tostring&vote=down "Vote down!")

3


[**_zikro32 at gmail dot com_**](https://www.php.net/manual/en/stringable.tostring.php#129691) [¶](https://www.php.net/manual/en/stringable.tostring.php#129691)

**1 year ago**

`__toString() magic method is not intended to be called directly.
Instead, it defines what is returned when the object is cast to string, either explicitly casting with:
(string)$element
Or implicitly, when used in certain contexts which would cause a conversion to string.
If you really want to explicitly call a method to convert an object to string, then you can just create a public toString method and call that, avoid using the magic __toString directly if no casting is needed.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=stringable.tostring&repo=en&redirect=https://www.php.net/manual/en/stringable.tostring.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google