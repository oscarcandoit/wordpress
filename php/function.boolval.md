---
url: https://www.php.net/manual/en/function.boolval.php
scraped_at: 2025-10-20T02:51:14.521Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# boolval

(PHP 5 >= 5.5.0, PHP 7, PHP 8)

boolval — Get the boolean value of a variable

### Description [¶](https://www.php.net/manual/en/function.boolval.php\#refsect1-function.boolval-description)

**boolval**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Returns the [bool](https://www.php.net/manual/en/language.types.boolean.php) value of `value`.


### Parameters [¶](https://www.php.net/manual/en/function.boolval.php\#refsect1-function.boolval-parameters)

`value`

The scalar value being converted to a [bool](https://www.php.net/manual/en/language.types.boolean.php).


### Return Values [¶](https://www.php.net/manual/en/function.boolval.php\#refsect1-function.boolval-returnvalues)

The [bool](https://www.php.net/manual/en/language.types.boolean.php) value of `value`.


### Examples [¶](https://www.php.net/manual/en/function.boolval.php\#refsect1-function.boolval-examples)

**Example #1 **boolval()** examples**

`<?php
echo '0:        '.(boolval(0) ? 'true' : 'false')."\n";
echo '42:       '.(boolval(42) ? 'true' : 'false')."\n";
echo '0.0:      '.(boolval(0.0) ? 'true' : 'false')."\n";
echo '4.2:      '.(boolval(4.2) ? 'true' : 'false')."\n";
echo '"":       '.(boolval("") ? 'true' : 'false')."\n";
echo '"string": '.(boolval("string") ? 'true' : 'false')."\n";
echo '"0":      '.(boolval("0") ? 'true' : 'false')."\n";
echo '"1":      '.(boolval("1") ? 'true' : 'false')."\n";
echo '[1, 2]:   '.(boolval([1, 2]) ? 'true' : 'false')."\n";
echo '[]:       '.(boolval([]) ? 'true' : 'false')."\n";
echo 'stdClass: '.(boolval(new stdClass) ? 'true' : 'false')."\n";
?>`

Run code

The above example will output:

```
0:        false
42:       true
0.0:      false
4.2:      true
"":       false
"string": true
"0":      false
"1":      true
[1, 2]:   true
[]:       false
stdClass: true
```

### See Also [¶](https://www.php.net/manual/en/function.boolval.php\#refsect1-function.boolval-seealso)

- [floatval()](https://www.php.net/manual/en/function.floatval.php) \- Get float value of a variable
- [intval()](https://www.php.net/manual/en/function.intval.php) \- Get the integer value of a variable
- [strval()](https://www.php.net/manual/en/function.strval.php) \- Get string value of a variable
- [settype()](https://www.php.net/manual/en/function.settype.php) \- Set the type of a variable
- [is\_bool()](https://www.php.net/manual/en/function.is-bool.php) \- Finds out whether a variable is a boolean
- [Type juggling](https://www.php.net/manual/en/language.types.type-juggling.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/boolval.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.boolval%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.boolval&repo=en&redirect=https://www.php.net/manual/en/function.boolval.php)

### User Contributed Notes 7 notes

[up](https://www.php.net/manual/vote-note.php?id=116477&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116477&page=function.boolval&vote=down "Vote down!")

59


[**_Matt M_**](https://www.php.net/manual/en/function.boolval.php#116477) [¶](https://www.php.net/manual/en/function.boolval.php#116477)

**10 years ago**

`To anyone like me who came here looking for a way to turn any value into a 0/1 that will fit into a MySQL boolean (tinyint) field:
<?php
$tinyint = (int) filter_var($valToCheck, FILTER_VALIDATE_BOOLEAN);
?>
tinyint will be 0 (zero) for values like string "false", boolean false, int 0
tinyint will be 1 for values like string "true", boolean true, int 1
Useful if you are accepting data that might be from a language like Javascript that sends string "false" for a boolean false.`

[up](https://www.php.net/manual/vote-note.php?id=125943&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=125943&page=function.boolval&vote=down "Vote down!")

53


[**_Anonymous_**](https://www.php.net/manual/en/function.boolval.php#125943) [¶](https://www.php.net/manual/en/function.boolval.php#125943)

**4 years ago**

`boolval('false') returns true.
boolval('False') return true.`

[up](https://www.php.net/manual/vote-note.php?id=111674&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=111674&page=function.boolval&vote=down "Vote down!")

54


[**_info at lomalkin dot ru_**](https://www.php.net/manual/en/function.boolval.php#111674) [¶](https://www.php.net/manual/en/function.boolval.php#111674)

**12 years ago**

`<?
// Hack for old php versions to use boolval()
if (!function_exists('boolval')) {
        function boolval($val) {
                return (bool) $val;
        }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=116547&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=116547&page=function.boolval&vote=down "Vote down!")

25


[**_raphael.satyago_**](https://www.php.net/manual/en/function.boolval.php#116547) [¶](https://www.php.net/manual/en/function.boolval.php#116547)

**10 years ago**

`function is_true($val, $return_null=false){
    $boolval = ( is_string($val) ? filter_var($val, FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE) : (bool) $val );
    return ( $boolval===null && !$return_null ? false : $boolval );
}
// Return Values:
is_true(new stdClass);      // true
is_true([1,2]);             // true
is_true([1]);               // true
is_true([0]);               // true
is_true(42);                // true
is_true(-42);               // true
is_true('true');            // true
is_true('on')               // true
is_true('off')              // false
is_true('yes')              // true
is_true('no')               // false
is_true('ja')               // false
is_true('nein')             // false
is_true('1');               // true
is_true(NULL);              // false
is_true(0);                 // false
is_true('false');           // false
is_true('string');          // false
is_true('0.0');             // false
is_true('4.2');             // false
is_true('0');               // false
is_true('');                // false
is_true([]);                // false`

[up](https://www.php.net/manual/vote-note.php?id=115017&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=115017&page=function.boolval&vote=down "Vote down!")

23


[**_Babak Bandpey_**](https://www.php.net/manual/en/function.boolval.php#115017) [¶](https://www.php.net/manual/en/function.boolval.php#115017)

**11 years ago**

`I believe that the double negation !! can perform the same task with the same result if your PHP is not up2date
var_dump(!!1, !!0, !!"test", !!"");
outputs:
boolean true
boolean false
boolean true
boolean false
May the life be good to you.`

[up](https://www.php.net/manual/vote-note.php?id=124657&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124657&page=function.boolval&vote=down "Vote down!")

9


[**_uasenior at gmail dot com_**](https://www.php.net/manual/en/function.boolval.php#124657) [¶](https://www.php.net/manual/en/function.boolval.php#124657)

**5 years ago**

`<?
// Some way to print boolean value as string
$b = true;
echo ['false', 'true'][$b];
?>`

[up](https://www.php.net/manual/vote-note.php?id=114013&page=function.boolval&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=114013&page=function.boolval&vote=down "Vote down!")

 -4


[**_Anonymous_**](https://www.php.net/manual/en/function.boolval.php#114013) [¶](https://www.php.net/manual/en/function.boolval.php#114013)

**11 years ago**

`A misspell in v2.0.
:-)
Hack v2.1
<?php
if( ! function_exists('boolval'))
{
    /**
     * Get the boolean value of a variable
     *
     * @param mixed The scalar value being converted to a boolean.
     * @return boolean The boolean value of var.
     */
    function boolval($var)
    {
        return !! $var;
    }
}
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.boolval&repo=en&redirect=https://www.php.net/manual/en/function.boolval.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google