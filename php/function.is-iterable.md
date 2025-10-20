---
url: https://www.php.net/manual/en/function.is-iterable.php
scraped_at: 2025-10-20T02:59:56.054Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_iterable

(PHP 7 >= 7.1.0, PHP 8)

is\_iterable —
Verify that the contents of a variable is an iterable value


### Description [¶](https://www.php.net/manual/en/function.is-iterable.php\#refsect1-function.is-iterable-description)

**is\_iterable**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Verify that the contents of a variable is accepted by the
[iterable](https://www.php.net/manual/en/language.types.iterable.php) pseudo-type, i.e. that it is either an [array](https://www.php.net/manual/en/language.types.array.php) or
an object implementing [Traversable](https://www.php.net/manual/en/class.traversable.php)

### Parameters [¶](https://www.php.net/manual/en/function.is-iterable.php\#refsect1-function.is-iterable-parameters)

`value`

The value to check


### Return Values [¶](https://www.php.net/manual/en/function.is-iterable.php\#refsect1-function.is-iterable-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `value` is iterable, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**
otherwise.


### Examples [¶](https://www.php.net/manual/en/function.is-iterable.php\#refsect1-function.is-iterable-examples)

**Example #1 **is\_iterable()** examples**

`<?php
var_dump(is_iterable([1, 2, 3]));  // bool(true)
var_dump(is_iterable(new ArrayIterator([1, 2, 3])));  // bool(true)
var_dump(is_iterable((function () { yield 1; })()));  // bool(true)
var_dump(is_iterable(1));  // bool(false)
var_dump(is_iterable(new stdClass()));  // bool(false)
?>`

Run code

### See Also [¶](https://www.php.net/manual/en/function.is-iterable.php\#refsect1-function.is-iterable-seealso)

- [is\_array()](https://www.php.net/manual/en/function.is-array.php) \- Finds whether a variable is an array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/is-iterable.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-iterable%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-iterable&repo=en&redirect=https://www.php.net/manual/en/function.is-iterable.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=122574&page=function.is-iterable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122574&page=function.is-iterable&vote=down "Vote down!")

35


[**_mopsyd at me dot com_**](https://www.php.net/manual/en/function.is-iterable.php#122574) [¶](https://www.php.net/manual/en/function.is-iterable.php#122574)

**7 years ago**

`A slight correction to brcontainer's polyfill, which prevents errors on a non-object in a non-blocking way, and also corrects the issue of  the conditional checking "file_exists" instead of the correct "function_exists":
if ( !function_exists(  'is_iterable' ) )
{
    function is_iterable( $obj )
    {
        return is_array( $obj ) || ( is_object( $obj ) && ( $obj instanceof \Traversable ) );
    }
}
The original answer would not have resolved correctly, because it was looking for a file instead of a function, and the provided method would error if given a non-iterable non-object value such as false.`

[up](https://www.php.net/manual/vote-note.php?id=122340&page=function.is-iterable&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=122340&page=function.is-iterable&vote=down "Vote down!")

 -2


[**_anatoly dot pashin at gmail dot com_**](https://www.php.net/manual/en/function.is-iterable.php#122340) [¶](https://www.php.net/manual/en/function.is-iterable.php#122340)

**7 years ago**

`Here is more details on iterable type: [http://php.net/manual/en/language.types.iterable.php](http://php.net/manual/en/language.types.iterable.php)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-iterable&repo=en&redirect=https://www.php.net/manual/en/function.is-iterable.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google