---
url: https://www.php.net/manual/en/function.compact.php
scraped_at: 2025-10-20T02:51:18.162Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# compact

(PHP 4, PHP 5, PHP 7, PHP 8)

compact — Create array containing variables and their values

### Description [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-description)

**compact**([array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `$var_name`, [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php) `...$var_names`): [array](https://www.php.net/manual/en/language.types.array.php)

Creates an array containing variables and their values.


For each of these, **compact()** looks for a
variable with that name in the current
[symbol table](https://www.php.net/manual/en/features.gc.refcounting-basics.php)
and adds it to the output array such that the variable name becomes the key
and the contents of the variable become the value for that key.
In short, it does the opposite of [extract()](https://www.php.net/manual/en/function.extract.php).


> **Note**:
>
>
> Before PHP 7.3, any strings that are not set will silently be skipped.

### Parameters [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-parameters)

`var_name``var_names`

**compact()** takes a variable number of parameters.
Each parameter can be either a string containing the name of the
variable, or an array of variable names. The array can contain other
arrays of variable names inside it; **compact()**
handles it recursively.


### Return Values [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-returnvalues)

Returns the output array with all the variables added to it.


### Errors/Exceptions [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-errors)

**compact()** issues an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** level error if a given string
refers to an unset variable.


### Changelog [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | If a given string references an unset variable, an **`[E\_WARNING](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-warning)`** level error is now issued. |
| 7.3.0 | **compact()** now issues an **`[E\_NOTICE](https://www.php.net/manual/en/errorfunc.constants.php#constant.e-notice)`** level error if a given string<br> refers to an unset variable. Formerly, such strings have been silently skipped. |

### Examples [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-examples)

**Example #1 **compact()** example**

`<?php
$city  = "San Francisco";
$state = "CA";
$event = "SIGGRAPH";
$location_vars = array("city", "state");
$result = compact("event", $location_vars);
print_r($result);
?>`

Run code

The above example will output:

```
Array
(
    [event] => SIGGRAPH
    [city] => San Francisco
    [state] => CA
)
```

### Notes [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-notes)

> **Note**:
> **Gotcha**
>
> Because [variable\\
> variables](https://www.php.net/manual/en/language.variables.variable.php) may not be used with PHP's
> [Superglobal\\
> arrays](https://www.php.net/manual/en/language.variables.superglobals.php) within functions, the Superglobal arrays may not be passed
> into **compact()**.

### See Also [¶](https://www.php.net/manual/en/function.compact.php\#refsect1-function.compact-seealso)

- [extract()](https://www.php.net/manual/en/function.extract.php) \- Import variables into the current symbol table from an array

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/array/functions/compact.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.compact%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.compact&repo=en&redirect=https://www.php.net/manual/en/function.compact.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=75334&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=75334&page=function.compact&vote=down "Vote down!")

179


[**_M Spreij_**](https://www.php.net/manual/en/function.compact.php#75334) [¶](https://www.php.net/manual/en/function.compact.php#75334)

**18 years ago**

`Can also handy for debugging, to quickly show a bunch of variables and their values:
<?php
print_r(compact(explode(' ', 'count acw cols coldepth')));
?>
gives
Array
(
    [count] => 70
    [acw] => 9
    [cols] => 7
    [coldepth] => 10
)`

[up](https://www.php.net/manual/vote-note.php?id=124607&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124607&page=function.compact&vote=down "Vote down!")

68


[**_lekiagospel at gmail dot com_**](https://www.php.net/manual/en/function.compact.php#124607) [¶](https://www.php.net/manual/en/function.compact.php#124607)

**5 years ago**

`Consider these two examples. The first as used in the manual, and  the second a slight variation of it.
Example #1
<?php
$city  = "San Francisco";
$state = "CA";
$event = "SIGGRAPH";
$location_vars = array("city", "state");
$result = compact("event", $location_vars);
print_r($result);
?>
Example #1 above  will output:
Array
(
    [event] => SIGGRAPH
    [city] => San Francisco
    [state] => CA
)
Example #2
<?php
$city  = "San Francisco";
$state = "CA";
$event = "SIGGRAPH";
$location_vars = array("city", "state");
$result = compact("event", "location_vars");
print_r($result);
?>
Example #2 above will output:
Array
(
    [event] => SIGGRAPH
    [location_vars] => Array
        (
            [0] => city
            [1] => state
        )
)
In the first example, the value of the variable $location_values (which is an array containing city, and state) is passed to compact().
In the second example, the name of the variable $location_vars  (i.e  without the '$' sign) is passed to compact() as a string. I hope this further clarifies the points made in the manual?`

[up](https://www.php.net/manual/vote-note.php?id=118723&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=118723&page=function.compact&vote=down "Vote down!")

60


[**_jmarkmurph at yahoo dot com_**](https://www.php.net/manual/en/function.compact.php#118723) [¶](https://www.php.net/manual/en/function.compact.php#118723)

**9 years ago**

`So compact('var1', 'var2') is the same as saying array('var1' => $var1, 'var2' => $var2) as long as $var1 and $var2 are set.`

[up](https://www.php.net/manual/vote-note.php?id=128903&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128903&page=function.compact&vote=down "Vote down!")

3


[**_c dot smith at fantasticmedia dot co dot uk_**](https://www.php.net/manual/en/function.compact.php#128903) [¶](https://www.php.net/manual/en/function.compact.php#128903)

**2 years ago**

`If you must utilise this knowing that a variable may be unset, then you need to use an alternative method.
So instead of the following:
<?php
$var1 = "lorem";
$var2 = "ipsum";
$result = compact('var1', 'var2', 'unsetvar');
?>
Consider the following:
<?php
$var1 = "lorem";
$var2 = "ipsum";
$result = [];
foreach( ['var1', 'var2', 'unsetvar'] as $attr ) {
    if ( isset( $$attr ) ) {
        $result[ $attr ] = $$attr;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=101954&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101954&page=function.compact&vote=down "Vote down!")

25


[**_Robc_**](https://www.php.net/manual/en/function.compact.php#101954) [¶](https://www.php.net/manual/en/function.compact.php#101954)

**14 years ago**

`The description says that compact is the opposite of extract() but it is important to understand that it does not completely reverse extract().  In particluar compact() does not unset() the argument variables given to it (and that extract() may have created).  If you want the individual variables to be unset after they are combined into an array then you have to do that yourself.`

[up](https://www.php.net/manual/vote-note.php?id=130437&page=function.compact&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=130437&page=function.compact&vote=down "Vote down!")

1


[**_jpitoniak at gmail dot com_**](https://www.php.net/manual/en/function.compact.php#130437) [¶](https://www.php.net/manual/en/function.compact.php#130437)

**2 months ago**

`If you want to collect all of the variables defined in the current scope into an array, use get_defined_vars().  It works similar to compact(), but doesn't require a list of variables to be passed.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.compact&repo=en&redirect=https://www.php.net/manual/en/function.compact.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google