---
url: https://www.php.net/manual/en/language.types.iterable.php
scraped_at: 2025-10-20T02:38:43.021Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Iterables [¶](https://www.php.net/manual/en/language.types.iterable.php\#language.types.iterable)

[Iterable](https://www.php.net/manual/en/language.types.iterable.php) is a built-in compile time type alias for

`array|Traversable`.
From its introduction in PHP 7.1.0 and prior to PHP 8.2.0,
[iterable](https://www.php.net/manual/en/language.types.iterable.php) was a built-in pseudo-type that acted as the
aforementioned type alias and can be used as a type declaration.
An iterable type can be used in [`foreach`](https://www.php.net/manual/en/control-structures.foreach.php) and with
**yield from** within a
[generator](https://www.php.net/manual/en/language.generators.php).


> **Note**:
>
>
> Functions declaring iterable as a return type may also be [generators](https://www.php.net/manual/en/language.generators.php).
>
>
>
> **Example #1**
> **Iterable generator return type example**
>
> `<?php
> function gen(): iterable {
>     yield 1;
>     yield 2;
>     yield 3;
> }
> foreach(gen() as $value) {
>     echo $value, "\n";
> }
> ?>`
>
> Run code

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/iterable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.iterable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.iterable&repo=en&redirect=https://www.php.net/manual/en/language.types.iterable.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google