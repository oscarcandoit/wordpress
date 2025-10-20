---
url: https://www.php.net/manual/en/language.types.enumerations.php
scraped_at: 2025-10-20T02:31:29.455Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Enumerations [¶](https://www.php.net/manual/en/language.types.enumerations.php\#language.types.enumerations)

(PHP 8 >= 8.1.0)

### Basic Enumerations [¶](https://www.php.net/manual/en/language.types.enumerations.php\#language.types.enumerations.basics)

Enumerations are a restricting layer on top of classes and class constants,
intended to provide a way to define a closed set of possible values for a type.


`<?php
enum Suit
{
    case Hearts;
    case Diamonds;
    case Clubs;
    case Spades;
}
function do_stuff(Suit $s)
{
    // ...
}
do_stuff(Suit::Spades);
?>`

Run code

For a full discussion, see the
[Enumerations](https://www.php.net/manual/en/language.enumerations.php) chapter.


### Casting [¶](https://www.php.net/manual/en/language.types.enumerations.php\#language.types.enumerations.casting)

If an enum is converted to an [object](https://www.php.net/manual/en/language.types.object.php), it is not
modified. If an enum is converted to an [array](https://www.php.net/manual/en/language.types.array.php),
an array with a single `name` key (for Pure enums) or
an array with both `name` and `value` keys
(for Backed enums) is created. All other cast types will result in an error.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/enumerations.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.enumerations%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.enumerations&repo=en&redirect=https://www.php.net/manual/en/language.types.enumerations.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=127105&page=language.types.enumerations&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127105&page=language.types.enumerations&vote=down "Vote down!")

55


[**_esdras-schonevald_**](https://www.php.net/manual/en/language.types.enumerations.php#127105) [¶](https://www.php.net/manual/en/language.types.enumerations.php#127105)

**3 years ago**

`[https://gist.github.com/esdras-schonevald/71a6730e6191c5e9c053e2f65b839eec](https://gist.github.com/esdras-schonevald/71a6730e6191c5e9c053e2f65b839eec)
<?php
declare(strict_types=1);
/**
* This is a sample
* How to use Enum to create a custom exception cases
* PHP 8.1^
*/
enum MyExceptionCase {
    case InvalidMethod;
    case InvalidProperty;
    case Timeout;
}
class MyException extends Exception {
    function __construct(private MyExceptionCase $case){
        match($case){
            MyExceptionCase::InvalidMethod      =>    parent::__construct("Bad Request - Invalid Method", 400),
            MyExceptionCase::InvalidProperty    =>    parent::__construct("Bad Request - Invalid Property", 400),
            MyExceptionCase::Timeout            =>    parent::__construct("Bad Request - Timeout", 400)
        };
    }
}
// Testing my custom exception class
try {
    throw new MyException(MyExceptionCase::InvalidMethod);
} catch (MyException $myE) {
    echo $myE->getMessage();  // Bad Request - Invalid Method
}`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.enumerations&repo=en&redirect=https://www.php.net/manual/en/language.types.enumerations.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google