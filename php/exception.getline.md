---
url: https://www.php.net/manual/en/exception.getline.php
scraped_at: 2025-10-20T02:50:19.149Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Exception::getLine

(PHP 5, PHP 7, PHP 8)

Exception::getLine — Gets the line in which the exception was created

### Description [¶](https://www.php.net/manual/en/exception.getline.php\#refsect1-exception.getline-description)

finalpublic**Exception::getLine**(): [int](https://www.php.net/manual/en/language.types.integer.php)

Get line number where the exception was created.


### Parameters [¶](https://www.php.net/manual/en/exception.getline.php\#refsect1-exception.getline-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/exception.getline.php\#refsect1-exception.getline-returnvalues)

Returns the line number where the exception was created.


### Examples [¶](https://www.php.net/manual/en/exception.getline.php\#refsect1-exception.getline-examples)

**Example #1 **Exception::getLine()** example**

`<?php
try {
    throw new Exception("Some error message");
} catch(Exception $e) {
    echo "The exception was created on line: " . $e->getLine();
}
?>`

The above example will output
something similar to:

```
The exception was created on line: 3
```

### See Also [¶](https://www.php.net/manual/en/exception.getline.php\#refsect1-exception.getline-seealso)

- [Throwable::getLine()](https://www.php.net/manual/en/throwable.getline.php) \- Gets the line on which the object was instantiated

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/exception/getline.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fexception.getline%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=exception.getline&repo=en&redirect=https://www.php.net/manual/en/exception.getline.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google