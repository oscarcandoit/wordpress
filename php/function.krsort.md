---
url: https://www.php.net/manual/en/function.krsort.php
scraped_at: 2025-10-20T02:49:27.340Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# krsort

(PHP 4, PHP 5, PHP 7, PHP 8)

krsort — Sort an array by key in descending order

### Description [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-description)

**krsort**([array](https://www.php.net/manual/en/language.types.array.php) `&$array`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`**): [true](https://www.php.net/manual/en/language.types.singleton.php)

Sorts `array` in place by keys
in descending order.


> **Note**:
>
>
> If two members compare as equal, they retain their original order.
> Prior to PHP 8.0.0, their relative order in the sorted array was undefined.

> **Note**:
>
>
> Resets array's internal pointer to the first element.

### Parameters [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-parameters)

`array`

The input array.


`flags`

The optional second parameter `flags`
may be used to modify the sorting behavior using these values:


Sorting type flags:


- **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** \- compare items normally;
the details are described in the [comparison operators](https://www.php.net/manual/en/language.operators.comparison.php) section
- **`[SORT\_NUMERIC](https://www.php.net/manual/en/array.constants.php#constant.sort-numeric)`** \- compare items numerically
- **`[SORT\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-string)`** \- compare items as strings
- **`[SORT\_LOCALE\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-locale-string)`** \- compare items as
strings, based on the current locale. It uses the locale,
which can be changed using [setlocale()](https://www.php.net/manual/en/function.setlocale.php)
- **`[SORT\_NATURAL](https://www.php.net/manual/en/array.constants.php#constant.sort-natural)`** \- compare items as strings
using "natural ordering" like [natsort()](https://www.php.net/manual/en/function.natsort.php)
- **`[SORT\_FLAG\_CASE](https://www.php.net/manual/en/array.constants.php#constant.sort-flag-case)`** \- can be combined
(bitwise OR) with
**`[SORT\_STRING](https://www.php.net/manual/en/array.constants.php#constant.sort-string)`** or
**`[SORT\_NATURAL](https://www.php.net/manual/en/array.constants.php#constant.sort-natural)`** to sort strings case-insensitively


### Return Values [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-returnvalues)

Always returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**.


### Changelog [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-changelog)

| Version | Description |
| --- | --- |
| 8.2.0 | The return type is **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** now; previously, it was [bool](https://www.php.net/manual/en/language.types.boolean.php). |
| 8.2.0 | This function now does numeric string comparison under<br> **`[SORT\_REGULAR](https://www.php.net/manual/en/array.constants.php#constant.sort-regular)`** using the standard PHP 8 rules. |

### Examples [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-examples)

**Example #1 **krsort()** example**

`<?php
$fruits = array("d"=>"lemon", "a"=>"orange", "b"=>"banana", "c"=>"apple");
krsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>`

Run code

The above example will output:

```
d = lemon
c = apple
b = banana
a = orange
```

### See Also [¶](https://www.php.net/manual/en/function.krsort.php\#refsect1-function.krsort-seealso)

- [sort()](https://www.php.net/manual/en/function.sort.php) \- Sort an array in ascending order
- [ksort()](https://www.php.net/manual/en/function.ksort.php) \- Sort an array by key in ascending order
- The [comparison of array sorting functions](https://www.php.net/manual/en/array.sorting.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/krsort.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.krsort%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.krsort&repo=en&redirect=https://www.php.net/manual/en/function.krsort.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google