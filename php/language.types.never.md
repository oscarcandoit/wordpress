---
url: https://www.php.net/manual/en/language.types.never.php
scraped_at: 2025-10-20T02:32:04.068Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Never [¶](https://www.php.net/manual/en/language.types.never.php\#language.types.never)

[never](https://www.php.net/manual/en/language.types.never.php) is a return-only type indicating the function
does not terminate. This means that it either calls [exit()](https://www.php.net/manual/en/function.exit.php),
throws an exception, or is an infinite loop.
Therefore, it cannot be part of a
[union type](https://www.php.net/manual/en/language.types.type-system.php#language.types.type-system.composite.union)
declaration. Available as of PHP 8.1.0.


[never](https://www.php.net/manual/en/language.types.never.php) is, in type theory parlance, the bottom type.
Meaning it is the subtype of every other type and can replace any other
return type during inheritance.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/never.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.never%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.never&repo=en&redirect=https://www.php.net/manual/en/language.types.never.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=128259&page=language.types.never&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128259&page=language.types.never&vote=down "Vote down!")

28


[**_ali1289445 at gmail dot com_**](https://www.php.net/manual/en/language.types.never.php#128259) [¶](https://www.php.net/manual/en/language.types.never.php#128259)

**2 years ago**

`<?php
function sayHello(string $name): never
{
    echo "Hello, $name";
    exit(); // if we comment this line, php throws fatal error
}
sayHello("John"); // result: "Hello, John"`

[up](https://www.php.net/manual/vote-note.php?id=129805&page=language.types.never&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129805&page=language.types.never&vote=down "Vote down!")

1


[**_dcfynn at icloud dot com_**](https://www.php.net/manual/en/language.types.never.php#129805) [¶](https://www.php.net/manual/en/language.types.never.php#129805)

**1 year ago**

`I think the description should be corrected from return-only to non-return function since the context is now misleading`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.never&repo=en&redirect=https://www.php.net/manual/en/language.types.never.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google