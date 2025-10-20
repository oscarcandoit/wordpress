---
url: https://www.php.net/manual/en/function.explode.php
scraped_at: 2025-10-20T02:57:30.336Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# explode

(PHP 4, PHP 5, PHP 7, PHP 8)

explode — Split a string by a string

### Description [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-description)

**explode**([string](https://www.php.net/manual/en/language.types.string.php) `$separator`, [string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$limit` = **`[PHP\_INT\_MAX](https://www.php.net/manual/en/reserved.constants.php#constant.php-int-max)`**): [array](https://www.php.net/manual/en/language.types.array.php)

Returns an array of strings, each of which is a substring of
`string` formed by splitting it on
boundaries formed by the string `separator`.


### Parameters [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-parameters)

`separator`

The boundary string.


`string`

The input string.


`limit`

If `limit` is set and positive, the returned array will contain
a maximum of `limit` elements with the last
element containing the rest of `string`.


If the `limit` parameter is negative, all components
except the last - `limit` are returned.


If the `limit` parameter is zero, then this is treated as 1.


> **Note**:
>
>
> Prior to PHP 8.0, [implode()](https://www.php.net/manual/en/function.implode.php) accepted its parameters in either order.
> **explode()** has never supported this: you must ensure that the
> `separator` argument comes before the
> `string` argument.

### Return Values [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-returnvalues)

Returns an [array](https://www.php.net/manual/en/language.types.array.php) of [string](https://www.php.net/manual/en/language.types.string.php)s
created by splitting the `string` parameter on
boundaries formed by the `separator`.


If `separator` is an empty [string](https://www.php.net/manual/en/language.types.string.php) (""),
**explode()** throws a [ValueError](https://www.php.net/manual/en/class.valueerror.php).
If `separator` contains a value that is not
contained in `string` and a negative
`limit` is used, then an empty [array](https://www.php.net/manual/en/language.types.array.php) will be
returned, otherwise an [array](https://www.php.net/manual/en/language.types.array.php) containing
`string` will be returned. If `separator`
values appear at the start or end of `string`, said values
will be added as an empty [array](https://www.php.net/manual/en/language.types.array.php) value either in the first or last
position of the returned [array](https://www.php.net/manual/en/language.types.array.php) respectively.


### Changelog [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | **explode()** will now throw [ValueError](https://www.php.net/manual/en/class.valueerror.php)<br> when `separator` parameter is given an empty string<br> ( `""`).<br> Previously, **explode()** returned **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** instead. |

### Examples [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-examples)

**Example #1 **explode()** examples**

`<?php
// Example 1
$pizza  = "piece1 piece2 piece3 piece4 piece5 piece6";
$pieces = explode(" ", $pizza);
echo $pieces[0], PHP_EOL; // piece1
echo $pieces[1], PHP_EOL; // piece2
// Example 2
$data = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $data);
echo $user, PHP_EOL; // foo
echo $pass, PHP_EOL; // *
?>`

Run code

**Example #2 **explode()** return examples**

`<?php
/*
A string that doesn't contain the delimiter will simply
return a one-length array of the original string.
*/
$input1 = "hello";
$input2 = "hello,there";
$input3 = ',';
var_dump( explode( ',', $input1 ) );
var_dump( explode( ',', $input2 ) );
var_dump( explode( ',', $input3 ) );
?>`

Run code

The above example will output:

```
array(1)
(
    [0] => string(5) "hello"
)
array(2)
(
    [0] => string(5) "hello"
    [1] => string(5) "there"
)
array(2)
(
    [0] => string(0) ""
    [1] => string(0) ""
)
```

**Example #3 `limit` parameter examples**

`<?php
$str = 'one|two|three|four';
// positive limit
print_r(explode('|', $str, 2));
// negative limit
print_r(explode('|', $str, -1));
?>`

Run code

The above example will output:

```
Array
(
    [0] => one
    [1] => two|three|four
)
Array
(
    [0] => one
    [1] => two
    [2] => three
)
```

### Notes [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-notes)

> **Note**: This function is
> binary-safe.

### See Also [¶](https://www.php.net/manual/en/function.explode.php\#refsect1-function.explode-seealso)

- [preg\_split()](https://www.php.net/manual/en/function.preg-split.php) \- Split string by a regular expression
- [str\_split()](https://www.php.net/manual/en/function.str-split.php) \- Convert a string to an array
- [mb\_split()](https://www.php.net/manual/en/function.mb-split.php) \- Split multibyte string using regular expression
- [str\_word\_count()](https://www.php.net/manual/en/function.str-word-count.php) \- Return information about words used in a string
- [strtok()](https://www.php.net/manual/en/function.strtok.php) \- Tokenize string
- [implode()](https://www.php.net/manual/en/function.implode.php) \- Join array elements with a string

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/explode.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.explode%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.explode&repo=en&redirect=https://www.php.net/manual/en/function.explode.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=126941&page=function.explode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126941&page=function.explode&vote=down "Vote down!")

39


[**_Gerben_**](https://www.php.net/manual/en/function.explode.php#126941) [¶](https://www.php.net/manual/en/function.explode.php#126941)

**3 years ago**

`Note that an empty input string will still result in one element in the output array. This is something to remember when you are processing unknown input.
For example, maybe you are splitting part of a URI by forward slashes (like "articles/42/show" => ["articles", "42", "show"]). And maybe you expect that an empty URI will result in an empty array ("" => []). Instead, it will contain one element, with an empty string:
<?php
$uri = '';
$parts = explode('/', $uri);
var_dump($parts);
?>
Will output:
array(1) {
[0]=>
string(0) ""
}
And not:
array(0) {
}`

[up](https://www.php.net/manual/vote-note.php?id=129028&page=function.explode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129028&page=function.explode&vote=down "Vote down!")

16


[**_marc_**](https://www.php.net/manual/en/function.explode.php#129028) [¶](https://www.php.net/manual/en/function.explode.php#129028)

**1 year ago**

`If your data is smaller than the expected count with the list expansion:
<?php
$data = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell,$nu) = explode(":", $data);
?>
The result is a warning not an error:
PHP Warning:  Undefined array key 7 in ...
The solution is to pad the array to the expected length:
<?php
$data = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell,$nu) = array_pad( explode(":", $data), 8, "");
// where 8 is the count of the list arguments
?>`

[up](https://www.php.net/manual/vote-note.php?id=125805&page=function.explode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125805&page=function.explode&vote=down "Vote down!")

12


[**_bocoroth_**](https://www.php.net/manual/en/function.explode.php#125805) [¶](https://www.php.net/manual/en/function.explode.php#125805)

**4 years ago**

`Be careful, while most non-alphanumeric data types as input strings return an array with an empty string when used with a valid separator, true returns an array with the string "1"!
var_dump(explode(',', null)); //array(1) { [0]=> string(0) "" }
var_dump(explode(',', false)); //array(1) { [0]=> string(0) "" }
var_dump(explode(',', true)); //array(1) { [0]=> string(1) "1" }`

[up](https://www.php.net/manual/vote-note.php?id=127698&page=function.explode&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127698&page=function.explode&vote=down "Vote down!")

3


[**_Alejandro-Ihuit_**](https://www.php.net/manual/en/function.explode.php#127698) [¶](https://www.php.net/manual/en/function.explode.php#127698)

**3 years ago**

`If you want to directly take a specific value without having to store it in another variable, you can implement the following:
$status = 'Missing-1';

echo $status_only = explode('-', $status)[0];
// Missing`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.explode&repo=en&redirect=https://www.php.net/manual/en/function.explode.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google