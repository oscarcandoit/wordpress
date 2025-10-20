---
url: https://www.php.net/manual/en/language.types.void.php
scraped_at: 2025-10-20T02:34:01.860Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Void [¶](https://www.php.net/manual/en/language.types.void.php\#language.types.void)

[void](https://www.php.net/manual/en/language.types.void.php) is a return-only type declaration indicating the
function does not return a value, but the function may still terminate.
Therefore, it cannot be part of a
[union type](https://www.php.net/manual/en/language.types.type-system.php#language.types.type-system.composite.union)
declaration. Available as of PHP 7.1.0.


> **Note**:
>
> Even if a function has a return type of [void](https://www.php.net/manual/en/language.types.void.php) it will
> still return a value, this value is always **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/void.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.void%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.void&repo=en&redirect=https://www.php.net/manual/en/language.types.void.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=130486&page=language.types.void&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130486&page=language.types.void&vote=down "Vote down!")

1


[**_harl at gmail dot com_**](https://www.php.net/manual/en/language.types.void.php#130486) [¶](https://www.php.net/manual/en/language.types.void.php#130486)

**1 month ago**

``"Even if a function has a return type of void it will still return a value, this value is always null."
Syntactically, a void-returning function's return statements must be plain `return;`. If the function is declared as returning null then the return statement needs to include a return value: `return null;`.
A function that always returns null ("function foo(): null {...}") is equivalent to a void-returning function ("function foo(): void {...}"). Neither actually returns any information to the caller (the caller always receives null, and doesn't learn anything from it).
Meaningful return type declarations using null are always union types. "function foo(): null" is legal but pointless and might as well be written as returning void to make explicit the fact that it doesn't return anything meaningful (and indicates that "$v = foo();" is certainly a mistake of some sort.) The exception to this is if foo() is a subclass method overriding a wider-but-still-nullable type from a superclass.
(And the technical reason why a void function still returns null is that a function call is an expression so needs to have SOME value if it returns at all.)``

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.void&repo=en&redirect=https://www.php.net/manual/en/language.types.void.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google