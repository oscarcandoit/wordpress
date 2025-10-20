---
url: https://www.php.net/manual/en/function.is-numeric.php
scraped_at: 2025-10-20T02:55:01.395Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# is\_numeric

(PHP 4, PHP 5, PHP 7, PHP 8)

is\_numeric —
Finds whether a variable is a number or a numeric string


### Description [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-description)

**is\_numeric**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Determines if the given variable is a number or a
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php).


### Parameters [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-parameters)

`value`

The variable being evaluated.


### Return Values [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** if `value` is a number or a
[numeric string](https://www.php.net/manual/en/language.types.numeric-strings.php),
**`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** otherwise.


### Changelog [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | Numeric strings ending with whitespace ( `"42 "`) will now<br> return **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**. Previously, **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** was returned instead. |

### Examples [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-examples)

**Example #1 **is\_numeric()** examples**

`<?php
$tests = array(
    "42",
    1337,
    0x539,
    02471,
    0b10100111001,
    1337e0,
    "0x539",
    "02471",
    "0b10100111001",
    "1337e0",
    "not numeric",
    array(),
    9.1,
    null,
    '',
);
foreach ($tests as $element) {
    if (is_numeric($element)) {
        echo var_export($element, true) . " is numeric", PHP_EOL;
    } else {
        echo var_export($element, true) . " is NOT numeric", PHP_EOL;
    }
}
?>`

Run code

The above example will output:

```
'42' is numeric
1337 is numeric
1337 is numeric
1337 is numeric
1337 is numeric
1337.0 is numeric
'0x539' is NOT numeric
'02471' is numeric
'0b10100111001' is NOT numeric
'1337e0' is numeric
'not numeric' is NOT numeric
array (
) is NOT numeric
9.1 is numeric
NULL is NOT numeric
'' is NOT numeric
```

**Example #2 **is\_numeric()** with whitespace**

`<?php
$tests = [\
    " 42",\
    "42 ",\
    "\u{A0}9001", // non-breaking space\
    "9001\u{A0}", // non-breaking space\
];
foreach ($tests as $element) {
    if (is_numeric($element)) {
        echo var_export($element, true) . " is numeric", PHP_EOL;
    } else {
        echo var_export($element, true) . " is NOT numeric", PHP_EOL;
    }
}
?>`

Run code

Output of the above example in PHP 8:

```
' 42' is numeric
'42 ' is numeric
' 9001' is NOT numeric
'9001 ' is NOT numeric
```

Output of the above example in PHP 7:

```
' 42' is numeric
'42 ' is NOT numeric
' 9001' is NOT numeric
'9001 ' is NOT numeric
```

### See Also [¶](https://www.php.net/manual/en/function.is-numeric.php\#refsect1-function.is-numeric-seealso)

- [Numeric strings](https://www.php.net/manual/en/language.types.numeric-strings.php)
- [ctype\_digit()](https://www.php.net/manual/en/function.ctype-digit.php) \- Check for numeric character(s)
- [is\_bool()](https://www.php.net/manual/en/function.is-bool.php) \- Finds out whether a variable is a boolean
- [is\_null()](https://www.php.net/manual/en/function.is-null.php) \- Finds whether a variable is null
- [is\_float()](https://www.php.net/manual/en/function.is-float.php) \- Finds whether the type of a variable is float
- [is\_int()](https://www.php.net/manual/en/function.is-int.php) \- Find whether the type of a variable is integer
- [is\_string()](https://www.php.net/manual/en/function.is-string.php) \- Find whether the type of a variable is string
- [is\_object()](https://www.php.net/manual/en/function.is-object.php) \- Finds whether a variable is an object
- [is\_array()](https://www.php.net/manual/en/function.is-array.php) \- Finds whether a variable is an array
- [filter\_var()](https://www.php.net/manual/en/function.filter-var.php) \- Filters a variable with a specified filter

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/is-numeric.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.is-numeric%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-numeric&repo=en&redirect=https://www.php.net/manual/en/function.is-numeric.php)

### User Contributed Notes 8 notes

[up](https://www.php.net/manual/vote-note.php?id=102011&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=102011&page=function.is-numeric&vote=down "Vote down!")

95


[**_sobolanx at gmail dot com_**](https://www.php.net/manual/en/function.is-numeric.php#102011) [¶](https://www.php.net/manual/en/function.is-numeric.php#102011)

**14 years ago**

`Note that the function accepts extremely big numbers and correctly evaluates them.
For example:
<?php
    $v = is_numeric ('58635272821786587286382824657568871098287278276543219876543') ? true : false;

    var_dump ($v);
?>
The above script will output:
bool(true)
So this function is not intimidated by super-big numbers. I hope this helps someone.
PS: Also note that if you write is_numeric (45thg), this will generate a parse error (since the parameter is not enclosed between apostrophes or double quotes). Keep this in mind when you use this function.`

[up](https://www.php.net/manual/vote-note.php?id=120584&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=120584&page=function.is-numeric&vote=down "Vote down!")

42


[**_tanguy\_barsik at hotmail dot com_**](https://www.php.net/manual/en/function.is-numeric.php#120584) [¶](https://www.php.net/manual/en/function.is-numeric.php#120584)

**8 years ago**

`for strings, it return true only if float number has a dot
is_numeric( '42.1' )//true
is_numeric( '42,1' )//false`

[up](https://www.php.net/manual/vote-note.php?id=69053&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=69053&page=function.is-numeric&vote=down "Vote down!")

12


[**_moskalyuk at gmail dot com_**](https://www.php.net/manual/en/function.is-numeric.php#69053) [¶](https://www.php.net/manual/en/function.is-numeric.php#69053)

**19 years ago**

`is_numeric fails on the hex values greater than LONG_MAX, so having a large hex value parsed through is_numeric would result in FALSE being returned even though the value is a valid hex number`

[up](https://www.php.net/manual/vote-note.php?id=114061&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114061&page=function.is-numeric&vote=down "Vote down!")

12


[**_ben at chico dot com_**](https://www.php.net/manual/en/function.is-numeric.php#114061) [¶](https://www.php.net/manual/en/function.is-numeric.php#114061)

**11 years ago**

`Apparently NAN (Not A Number) is a number for the sake of is_numeric().
<?php
echo "is ";
if (!is_numeric(NAN))
echo "not ";
echo "a number";
?>
Outputs "is a number". So something that is NOT a number (by defintion) is a number...`

[up](https://www.php.net/manual/vote-note.php?id=88041&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88041&page=function.is-numeric&vote=down "Vote down!")

5


[**_Magnus Deininger, dma05 at web dot de_**](https://www.php.net/manual/en/function.is-numeric.php#88041) [¶](https://www.php.net/manual/en/function.is-numeric.php#88041)

**16 years ago**

`regarding the global vs. american numeral notations, it should be noted that at least in japanese, numbers aren't grouped with an extra symbol every three digits, but rather every four digits (for example 1,0000 instead of 10.000). also nadim's regexen are slightly suboptimal at one point having an unescaped '.' operator, and the whole thing could easily be combined into a single regex (speed and all).
adjustments:
<?php
$eng_or_world = preg_match
('/^[+-]?'. // start marker and sign prefix
'(((([0-9]+)|([0-9]{1,4}(,[0-9]{3,4})+)))?(\\.[0-9])?([0-9]*)|'. // american
'((([0-9]+)|([0-9]{1,4}(\\.[0-9]{3,4})+)))?(,[0-9])?([0-9]*))'. // world
'(e[0-9]+)?'. // exponent
'$/', // end marker
$str) == 1;
?>
i'm sure this still isn't optimal, but it should also cover japanese-style numerals and it fixed a couple of other issues with the other regexen. it also allows for an exponent suffix, the pre-decimal digits are optional and it enforces using either grouped or ungrouped integer parts. should be easier to trim to your liking too.`

[up](https://www.php.net/manual/vote-note.php?id=37717&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=37717&page=function.is-numeric&vote=down "Vote down!")

6


[**_kouber at saparev dot com_**](https://www.php.net/manual/en/function.is-numeric.php#37717) [¶](https://www.php.net/manual/en/function.is-numeric.php#37717)

**21 years ago**

`Note that this function is not appropriate to check if "is_numeric" for very long strings. In fact, everything passed to this function is converted to long and then to a double. Anything greater than approximately 1.8e308 is too large for a double, so it becomes infinity, i.e. FALSE. What that means is that, for each string with more than 308 characters, is_numeric() will return FALSE, even if all chars are digits.
However, this behaviour is platform-specific.
[http://www.php.net/manual/en/language.types.float.php](http://www.php.net/manual/en/language.types.float.php)
In such a case, it is suitable to use regular expressions:
function is_numeric_big($s=0) {
return preg_match('/^-?\d+$/', $s);
}`

[up](https://www.php.net/manual/vote-note.php?id=130445&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130445&page=function.is-numeric&vote=down "Vote down!")

1


[**_makogon-vs at yandex dot ru_**](https://www.php.net/manual/en/function.is-numeric.php#130445) [¶](https://www.php.net/manual/en/function.is-numeric.php#130445)

**2 months ago**

`These functions are designed for precise number type validation:
isInteger checks if a value is an integer (including string representations of integers).
isFloat verifies if a value is a floating-point number (including string representations of decimals).
They handle all number formats (positive, negative, leading zeros, dots at start/end) while rejecting non-numeric values (booleans, arrays, null).
<?php
    function isInteger(mixed $val): bool
    {
        if (!is_scalar($val) || is_bool($val)) {
            return false;
        }
        if (is_int($val)) {
            return true;
        }
        if (isFloat($val)) {
            return false;
        }
        return preg_match('~^((?:\+|-)?[0-9]+)$~', (string) $val) === 1;
    }
    function isFloat(mixed $val): bool
    {
        if (!is_scalar($val) || is_bool($val)) {
            return false;
        }
        if (gettype($val) === "double") {
            return true;
        }
        if (!is_string($val)) {
            return false;
        }
        return preg_match('/^[+-]?(\d*\.\d+|\d+\.\d*)$/', $val) === 1;
    }
    $testValues = [\
        // Integers\
        42,                      // integer\
        '42',                    // string integer\
        '+42',                   // string with plus\
        '-42',                   // string with minus\
        '0042',                  // leading zeros\
        '000',                   // zeros\
        PHP_INT_MAX,             // maximum int\
        (string) PHP_INT_MAX,    // maximum int as string\
        // Floating point numbers\
        3.14,                    // float\
        '3.14',                  // string float\
        '.5',                    // without integer part\
        '5.',                    // without fractional part\
        '0.5',                   // with zero integer part\
        '5.0',                   // with zero fractional part\
        '+3.14',                 // with plus\
        '-3.14',                 // with minus\
        '0.0',                   // zero float\
        '00.5',                  // leading zeros in integer part\
        '5.00',                  // leading zeros in fractional part\
        '-.5',                   // negative without integer part\
        '-5.',                   // negative without fractional part\
        // Non-numbers\
        null,                    // null\
        [],                      // array\
        true,                    // boolean true\
        false,                   // boolean false\
        'string',                // regular string\
        '123abc',                // number with letters\
        '12.3.4',                // multiple dots\
        '++12',                  // double plus\
        '--12',                  // double minus\
        '12 ',                   // trailing space\
        ' 12',                   // leading space\
        '',                      // empty string\
        '1e5',                   // exponential notation\
        1e5,                     // float in exponential form\
    ];
    foreach ($testValues as $value) {
        $display = match (true) {
            is_null($value) => 'null',
            is_array($value) => '[]',
            is_bool($value) => $value ? 'true' : 'false',
            default => $value
        };
        $type = gettype($value);
        echo "$display: $type";
        echo " | isInteger: " . (isInteger($value) ? 'yes' : 'no');
        echo " | isFloat: " . (isFloat($value) ? 'yes' : 'no');
        echo PHP_EOL;
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=127989&page=function.is-numeric&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127989&page=function.is-numeric&vote=down "Vote down!")

 -2


[**_Katrina Kizenbach_**](https://www.php.net/manual/en/function.is-numeric.php#127989) [¶](https://www.php.net/manual/en/function.is-numeric.php#127989)

**2 years ago**

`Note that is_numeric() will evaluate to false for number strings using decimal commas.
is_numeric('0.11');
Output: true
is_numeric('0,11');
Output: false`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.is-numeric&repo=en&redirect=https://www.php.net/manual/en/function.is-numeric.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google