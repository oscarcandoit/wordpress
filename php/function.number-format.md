---
url: https://www.php.net/manual/en/function.number-format.php
scraped_at: 2025-10-20T02:58:06.867Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# number\_format

(PHP 4, PHP 5, PHP 7, PHP 8)

number\_format — Format a number with grouped thousands

### Description [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-description)

**number\_format**(

[float](https://www.php.net/manual/en/language.types.float.php) `$num`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$decimals` = 0,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$decimal_separator` = ".",

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$thousands_separator` = ","

): [string](https://www.php.net/manual/en/language.types.string.php)

Formats a number with grouped thousands and optionally decimal digits using the rounding half up rule.


### Parameters [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-parameters)

`num`

The number being formatted.


`decimals`

Sets the number of decimal digits.
If `0`, the `decimal_separator` is
omitted from the return value.
As of PHP 8.3.0, when the value is negative, `num`
is rounded to `decimals` significant digits before
the decimal point.
Prior to PHP 8.3.0, negative values were ignored and handled the
same as `0`.


`decimal_separator`

Sets the separator for the decimal point.


`thousands_separator`

Sets the thousands separator.


### Return Values [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-returnvalues)

A formatted version of `num`.


### Changelog [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-changelog)

| Version | Description |
| --- | --- |
| 8.3.0 | Added handling of negative values for `decimals`. |
| 8.0.0 | Prior to this version, **number\_format()** accepted<br> one, two, or four parameters (but not three). |
| 7.2.0 | **number\_format()** was changed to not being able to return <br> `-0`, previously `-0` could be returned <br> for cases like where `num` would be `-0.01`. |

### Examples [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-examples)

**Example #1 **number\_format()** Example**

For instance, French notation usually use two decimals,
comma (',') as decimal separator, and space (' ') as
thousand separator. The following example demonstrates various ways to format a number:


`<?php
$number = 1234.56;
// english notation (default)
echo number_format($number), PHP_EOL;
// 1,235
// French notation
echo number_format($number, 2, ',', ' '), PHP_EOL;
// 1 234,56
$number = 1234.5678;
// english notation without thousands separator
echo number_format($number, 2, '.', ''), PHP_EOL;
// 1234.57
?>`

Run code

**Example #2 A negative value for `decimals`**

As of PHP 8.3.0, a negative value for `decimals`
is used to round the number of significant digits before the decimal
point.


`<?php
$number = "1234.5678";
var_dump(number_format($number, -1));
var_dump(number_format($number, -2));
var_dump(number_format($number, -3));
?>`

Run code

The above example will output:

```
string(5) "1,230"
string(5) "1,200"
string(5) "1,000"
```

### See Also [¶](https://www.php.net/manual/en/function.number-format.php\#refsect1-function.number-format-seealso)

- [money\_format()](https://www.php.net/manual/en/function.money-format.php) \- Formats a number as a currency string
- [sprintf()](https://www.php.net/manual/en/function.sprintf.php) \- Return a formatted string
- [printf()](https://www.php.net/manual/en/function.printf.php) \- Output a formatted string
- [sscanf()](https://www.php.net/manual/en/function.sscanf.php) \- Parses input from a string according to a format

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/strings/functions/number-format.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.number-format%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.number-format&repo=en&redirect=https://www.php.net/manual/en/function.number-format.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=88424&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88424&page=function.number-format&vote=down "Vote down!")

427


[**_thomas at weblizards dot de_**](https://www.php.net/manual/en/function.number-format.php#88424) [¶](https://www.php.net/manual/en/function.number-format.php#88424)

**16 years ago**

`It's not explicitly documented; number_format also rounds:
<?php
$numbers = array(0.001, 0.002, 0.003, 0.004, 0.005, 0.006, 0.007, 0.008, 0.009);
foreach ($numbers as $number)
    print $number."->".number_format($number, 2, '.', ',')."<br>";
?>
0.001->0.00
0.002->0.00
0.003->0.00
0.004->0.00
0.005->0.01
0.006->0.01
0.007->0.01
0.008->0.01
0.009->0.01`

[up](https://www.php.net/manual/vote-note.php?id=126729&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=126729&page=function.number-format&vote=down "Vote down!")

10


[**_info at ensostudio dot ru_**](https://www.php.net/manual/en/function.number-format.php#126729) [¶](https://www.php.net/manual/en/function.number-format.php#126729)

**3 years ago**

`Note: use NumberFormatter to convert in human-readable format instead  user function from comments:
<?php
echo NumberFormatter::create('en', NumberFormatter::SPELLOUT)->format(12309); // twelve thousand three hundred nine
echo NumberFormatter::create('ru', NumberFormatter::SPELLOUT)->format(12307.5); //  двенадцать тысяч триста семь целых пять десятых
?>`

[up](https://www.php.net/manual/vote-note.php?id=89888&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89888&page=function.number-format&vote=down "Vote down!")

41


[**_james at bandit dot co.nz_**](https://www.php.net/manual/en/function.number-format.php#89888) [¶](https://www.php.net/manual/en/function.number-format.php#89888)

**16 years ago**

`Outputs a human readable number.
<?php
    #    Output easy-to-read numbers
    #    by james at bandit.co.nz
    function bd_nice_number($n) {
        // first strip any formatting;
        $n = (0+str_replace(",","",$n));

        // is this a number?
        if(!is_numeric($n)) return false;

        // now filter it;
        if($n>1000000000000) return round(($n/1000000000000),1).' trillion';
        else if($n>1000000000) return round(($n/1000000000),1).' billion';
        else if($n>1000000) return round(($n/1000000),1).' million';
        else if($n>1000) return round(($n/1000),1).' thousand';

        return number_format($n);
    }
?>
Outputs:
247,704,360 -> 247.7 million
866,965,260,000 -> 867 billion`

[up](https://www.php.net/manual/vote-note.php?id=62141&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62141&page=function.number-format&vote=down "Vote down!")

22


[**_MarcM_**](https://www.php.net/manual/en/function.number-format.php#62141) [¶](https://www.php.net/manual/en/function.number-format.php#62141)

**19 years ago**

`For Zero fill - just use the sprintf() function
$pr_id = 1;
$pr_id = sprintf("%03d", $pr_id);
echo $pr_id;
//outputs 001
-----------------
$pr_id = 10;
$pr_id = sprintf("%03d", $pr_id);
echo $pr_id;
//outputs 010
-----------------
You can change %03d to %04d, etc.`

[up](https://www.php.net/manual/vote-note.php?id=30643&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=30643&page=function.number-format&vote=down "Vote down!")

8


[**_Theo Diem_**](https://www.php.net/manual/en/function.number-format.php#30643) [¶](https://www.php.net/manual/en/function.number-format.php#30643)

**22 years ago**

`formatting numbers may be more easy if u use number_format function.
I also wrote this :
function something($number)
{
    $locale = localeconv();
    return number_format($number,
       $locale['frac_digits'],
        $locale['decimal_point'],
        $locale['thousands_sep']);
}
hope this helps =)
[]'s`

[up](https://www.php.net/manual/vote-note.php?id=57376&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=57376&page=function.number-format&vote=down "Vote down!")

5


[**_Jeroen de Bruijn \[NL\]_**](https://www.php.net/manual/en/function.number-format.php#57376) [¶](https://www.php.net/manual/en/function.number-format.php#57376)

**20 years ago**

`If you want to display a number ending with ,- (like 200,-) when there are no decimal characters and display the decimals when there are decimal characters i use:
function DisplayDouble($value)
{
list($whole, $decimals) = split ('[.,]', $value, 2);
if (intval($decimals) > 0)
    return number_format($value,2,".",",");
else
    return number_format($value,0,".",",") .",-";
}`

[up](https://www.php.net/manual/vote-note.php?id=52311&page=function.number-format&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=52311&page=function.number-format&vote=down "Vote down!")

13


[**_stm555 at hotmail dot com_**](https://www.php.net/manual/en/function.number-format.php#52311) [¶](https://www.php.net/manual/en/function.number-format.php#52311)

**20 years ago**

`I ran across an issue where I wanted to keep the entered precision of a real value, without arbitrarily rounding off what the user had submitted.
I figured it out with a quick explode on the number before formatting. I could then format either side of the decimal.
<?php
      function number_format_unlimited_precision($number,$decimal = '.')
      {
           $broken_number = explode($decimal,$number);
           return number_format($broken_number[0]).$decimal.$broken_number[1];
      }
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.number-format&repo=en&redirect=https://www.php.net/manual/en/function.number-format.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google