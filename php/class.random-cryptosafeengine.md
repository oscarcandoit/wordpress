---
url: https://www.php.net/manual/en/class.random-cryptosafeengine.php
scraped_at: 2025-10-20T02:38:40.871Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Random\\CryptoSafeEngine interface [¶](https://www.php.net/manual/en/class.random-cryptosafeengine.php\#class.random-cryptosafeengine)

(PHP 8 >= 8.2.0)

## Introduction [¶](https://www.php.net/manual/en/class.random-cryptosafeengine.php\#random-cryptosafeengine.intro)

A marker interface indicating that the [Random\\Engine](https://www.php.net/manual/en/class.random-engine.php) returns cryptographically secure randomness.


## Interface synopsis [¶](https://www.php.net/manual/en/class.random-cryptosafeengine.php\#random-cryptosafeengine.synopsis)

interface **Random\\CryptoSafeEngine** extends [Random\\Engine](https://www.php.net/manual/en/class.random-engine.php) {

/\\* Inherited methods \*/

public[Random\\Engine::generate](https://www.php.net/manual/en/random-engine.generate.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

}

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/random.cryptosafeengine.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.random-cryptosafeengine%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.random-cryptosafeengine&repo=en&redirect=https://www.php.net/manual/en/class.random-cryptosafeengine.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google