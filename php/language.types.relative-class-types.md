---
url: https://www.php.net/manual/en/language.types.relative-class-types.php
scraped_at: 2025-10-20T02:41:36.281Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Relative class types [¶](https://www.php.net/manual/en/language.types.relative-class-types.php\#language.types.relative-class-types)

These types declarations can only be used within classes.


### self [¶](https://www.php.net/manual/en/language.types.relative-class-types.php\#language.types.relative-class-types.self)

The value must be an [`instanceof`](https://www.php.net/manual/en/language.operators.type.php) the same class as the one
in which the type declaration is used.


### parent [¶](https://www.php.net/manual/en/language.types.relative-class-types.php\#language.types.relative-class-types.parent)

The value must be an [`instanceof`](https://www.php.net/manual/en/language.operators.type.php) a parent of the class
in which the type declaration is used.


### static [¶](https://www.php.net/manual/en/language.types.relative-class-types.php\#language.types.relative-class-types.static)

static is a return-only type which requires that the
value returned must be an [`instanceof`](https://www.php.net/manual/en/language.operators.type.php) the same class as the one
the method is called in.
Available as of PHP 8.0.0.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/relative-class-types.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.relative-class-types%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.relative-class-types&repo=en&redirect=https://www.php.net/manual/en/language.types.relative-class-types.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google