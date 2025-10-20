---
url: https://www.php.net/manual/en/function.gettype.php
scraped_at: 2025-10-20T02:59:42.159Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# gettype

(PHP 4, PHP 5, PHP 7, PHP 8)

gettype — Get the type of a variable

### Description [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-description)

**gettype**([mixed](https://www.php.net/manual/en/language.types.mixed.php) `$value`): [string](https://www.php.net/manual/en/language.types.string.php)

Returns the type of the PHP variable `value`. For
type checking, use `is_*` functions.


### Parameters [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-parameters)

`value`

The variable being type checked.


### Return Values [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-returnvalues)

Possible values for the returned string are:


- `"boolean"`
- `"integer"`
- `"double"` (for historical reasons `"double"` is
returned in case of a [float](https://www.php.net/manual/en/language.types.float.php), and not simply
`"float"`)

- `"string"`
- `"array"`
- `"object"`
- `"resource"`
- `"resource (closed)"` as of PHP 7.2.0

- `"NULL"`
- `"unknown type"`

### Changelog [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-changelog)

| Version | Description |
| --- | --- |
| 7.2.0 | Closed resources are now reported as `'resource (closed)'`.<br> Previously the returned value for closed resources were `'unknown type'`. |

### Examples [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-examples)

**Example #1 **gettype()** example**

`<?php
$data = array(1, 1., NULL, new stdClass, 'foo');
foreach ($data as $value) {
    echo gettype($value), "\n";
}
?>`

Run code

The above example will output
something similar to:

```
integer
double
NULL
object
string
```

### See Also [¶](https://www.php.net/manual/en/function.gettype.php\#refsect1-function.gettype-seealso)

- [get\_debug\_type()](https://www.php.net/manual/en/function.get-debug-type.php) \- Gets the type name of a variable in a way that is suitable for debugging
- [settype()](https://www.php.net/manual/en/function.settype.php) \- Set the type of a variable
- [get\_class()](https://www.php.net/manual/en/function.get-class.php) \- Returns the name of the class of an object
- [is\_array()](https://www.php.net/manual/en/function.is-array.php) \- Finds whether a variable is an array
- [is\_bool()](https://www.php.net/manual/en/function.is-bool.php) \- Finds out whether a variable is a boolean
- [is\_callable()](https://www.php.net/manual/en/function.is-callable.php) \- Verify that a value can be called as a function from the current scope
- [is\_float()](https://www.php.net/manual/en/function.is-float.php) \- Finds whether the type of a variable is float
- [is\_int()](https://www.php.net/manual/en/function.is-int.php) \- Find whether the type of a variable is integer
- [is\_null()](https://www.php.net/manual/en/function.is-null.php) \- Finds whether a variable is null
- [is\_numeric()](https://www.php.net/manual/en/function.is-numeric.php) \- Finds whether a variable is a number or a numeric string
- [is\_object()](https://www.php.net/manual/en/function.is-object.php) \- Finds whether a variable is an object
- [is\_resource()](https://www.php.net/manual/en/function.is-resource.php) \- Finds whether a variable is a resource
- [is\_scalar()](https://www.php.net/manual/en/function.is-scalar.php) \- Finds whether a variable is a scalar
- [is\_string()](https://www.php.net/manual/en/function.is-string.php) \- Find whether the type of a variable is string
- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php) \- Return true if the given function has been defined
- [method\_exists()](https://www.php.net/manual/en/function.method-exists.php) \- Checks if the class method exists

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/gettype.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.gettype%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gettype&repo=en&redirect=https://www.php.net/manual/en/function.gettype.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=128603&page=function.gettype&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128603&page=function.gettype&vote=down "Vote down!")

12


[**_mohammad dot alavi1990 at gmail dot com_**](https://www.php.net/manual/en/function.gettype.php#128603) [¶](https://www.php.net/manual/en/function.gettype.php#128603)

**2 years ago**

`Be careful comparing ReflectionParameter::getType() and gettype() as they will not return the same results for a given type.
string - string // OK
int - integer // Type mismatch
bool - boolean // Type mismatch
array - array // OK`

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.gettype&repo=en&redirect=https://www.php.net/manual/en/function.gettype.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google