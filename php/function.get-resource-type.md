---
url: https://www.php.net/manual/en/function.get-resource-type.php
scraped_at: 2025-10-20T02:36:32.037Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# get\_resource\_type

(PHP 4 >= 4.0.2, PHP 5, PHP 7, PHP 8)

get\_resource\_type —
Returns the resource type


### Description [¶](https://www.php.net/manual/en/function.get-resource-type.php\#refsect1-function.get-resource-type-description)

**get\_resource\_type**([resource](https://www.php.net/manual/en/language.types.resource.php) `$resource`): [string](https://www.php.net/manual/en/language.types.string.php)

This function gets the type of the given resource.


### Parameters [¶](https://www.php.net/manual/en/function.get-resource-type.php\#refsect1-function.get-resource-type-parameters)

`resource`

The evaluated resource handle.


### Return Values [¶](https://www.php.net/manual/en/function.get-resource-type.php\#refsect1-function.get-resource-type-returnvalues)

If the given `resource` is a resource, this function
will return a string representing its type. If the type is not identified
by this function, the return value will be the string
`Unknown`.


This function will return **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** and generate an error if
`resource` is not a [resource](https://www.php.net/manual/en/language.types.resource.php).


### Examples [¶](https://www.php.net/manual/en/function.get-resource-type.php\#refsect1-function.get-resource-type-examples)

**Example #1 **get\_resource\_type()** example**

`<?php
$fp = fopen("foo", "w");
echo get_resource_type($fp) . "\n";
?>`

Run code

Output of the above example in PHP 7:

```
stream
```

### See Also [¶](https://www.php.net/manual/en/function.get-resource-type.php\#refsect1-function.get-resource-type-seealso)

- [get\_resource\_id()](https://www.php.net/manual/en/function.get-resource-id.php) \- Returns an integer identifier for the given resource

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/var/functions/get-resource-type.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.get-resource-type%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.get-resource-type&repo=en&redirect=https://www.php.net/manual/en/function.get-resource-type.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google