---
url: https://www.php.net/manual/en/imagick.clone.php
scraped_at: 2025-10-20T02:52:50.032Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Imagick::clone

(PECL imagick 2, PECL imagick 3)

Imagick::clone — Makes an exact copy of the Imagick object

### Description [¶](https://www.php.net/manual/en/imagick.clone.php\#refsect1-imagick.clone-description)

public**Imagick::clone**(): [Imagick](https://www.php.net/manual/en/class.imagick.php)

Makes an exact copy of the Imagick object.


**Warning**

This function has been _DEPRECATED_ as of imagick 3.1.0
in favour of using the [clone](https://www.php.net/manual/en/language.oop5.cloning.php)
keyword.


### Parameters [¶](https://www.php.net/manual/en/imagick.clone.php\#refsect1-imagick.clone-parameters)

This function has no parameters.

### Return Values [¶](https://www.php.net/manual/en/imagick.clone.php\#refsect1-imagick.clone-returnvalues)

A copy of the Imagick object is returned.


### Changelog [¶](https://www.php.net/manual/en/imagick.clone.php\#refsect1-imagick.clone-changelog)

| Version | Description |
| --- | --- |
| PECL imagick 3.1.0 | The method was deprecated in favour of the<br> [clone](https://www.php.net/manual/en/language.oop5.cloning.php) keyword. |

### Examples [¶](https://www.php.net/manual/en/imagick.clone.php\#refsect1-imagick.clone-examples)

**Example #1 Imagick object cloning in different versions of imagick**

`<?php
// Cloning an Imagick object in imagick 2.x and 3.0:
$newImage = $image->clone();
// Cloning an Imagick object from 3.1.0 on:
$newImage = clone $image;
?>`

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/imagick/imagick/clone.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fimagick.clone%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=imagick.clone&repo=en&redirect=https://www.php.net/manual/en/imagick.clone.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google