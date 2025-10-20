---
url: https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php
scraped_at: 2025-10-20T03:01:37.672Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ReflectionParameter::getDefaultValueConstantName

(PHP 5 >= 5.4.6, PHP 7, PHP 8)

ReflectionParameter::getDefaultValueConstantName — Returns the default value's constant name if default value is constant or null

### Description [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-description)

public**ReflectionParameter::getDefaultValueConstantName**(): [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php)

Returns the default value's constant name of the parameter of any user-defined
or internal function or method, if default value is constant or null.
If the parameter is not optional a [ReflectionException](https://www.php.net/manual/en/class.reflectionexception.php)
will be thrown.


### Parameters [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-returnvalues)

Returns string on success or **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** on failure.


### Changelog [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-changelog)

| Version | Description |
| --- | --- |
| 8.0.0 | This method now allows getting the default values' constant names of built-in functions and<br> built-in class methods. Previously, a [ReflectionException](https://www.php.net/manual/en/class.reflectionexception.php) was thrown. |

### Examples [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-examples)

**Example #1 Getting default values' constant names of function parameters**

`<?php
function foo($test, $bar = PHP_INT_MIN)
{
    echo $test . $bar;
}
$function = new ReflectionFunction('foo');
foreach ($function->getParameters() as $param) {
    echo 'Name: ' . $param->getName() . PHP_EOL;
    if ($param->isOptional()) {
        echo 'Default value: ' . $param->getDefaultValueConstantName() . PHP_EOL;
    }
    echo PHP_EOL;
}
?>`

Run code

The above example will output:

```
Name: test

Name: bar
Default value: PHP_INT_MIN
```

### See Also [¶](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php\#refsect1-reflectionparameter.getdefaultvalueconstantname-seealso)

- [ReflectionParameter::isOptional()](https://www.php.net/manual/en/reflectionparameter.isoptional.php) \- Checks if optional
- [ReflectionParameter::isDefaultValueConstant()](https://www.php.net/manual/en/reflectionparameter.isdefaultvalueconstant.php) \- Returns whether the default value of this parameter is a constant
- [ReflectionParameter::getDefaultValue()](https://www.php.net/manual/en/reflectionparameter.getdefaultvalue.php) \- Gets default parameter value

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/reflection/reflectionparameter/getdefaultvalueconstantname.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Freflectionparameter.getdefaultvalueconstantname%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=reflectionparameter.getdefaultvalueconstantname&repo=en&redirect=https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google