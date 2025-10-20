---
url: https://www.php.net/manual/en/random.constants.php
scraped_at: 2025-10-20T02:41:14.764Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Predefined Constants [¶](https://www.php.net/manual/en/random.constants.php\#random.constants)

The constants below are always available as part of the PHP core.

**`[MT\_RAND\_MT19937](https://www.php.net/manual/en/random.constants.php#constant.mt-rand-mt19937)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that the correct [» Mt19937](http://www.math.sci.hiroshima-u.ac.jp/m-mat/MT/ARTICLES/mt.pdf) (Mersenne Twister)
implementation will be used by the algorithm, when creating a [Random\\Engine\\Mt19937](https://www.php.net/manual/en/class.random-engine-mt19937.php) instance
using [Random\\Engine\\Mt19937::\_\_construct()](https://www.php.net/manual/en/random-engine-mt19937.construct.php) or seeding the global Mersenne Twister
with [mt\_srand()](https://www.php.net/manual/en/function.mt-srand.php).
**`[MT\_RAND\_PHP](https://www.php.net/manual/en/random.constants.php#constant.mt-rand-php)`**
([int](https://www.php.net/manual/en/language.types.integer.php))

Indicates that an incorrect Mersenne Twister implementation will be used by the algorithm, when
creating a [Random\\Engine\\Mt19937](https://www.php.net/manual/en/class.random-engine-mt19937.php) instance using [Random\\Engine\\Mt19937::\_\_construct()](https://www.php.net/manual/en/random-engine-mt19937.construct.php)
or seeding the global Mersenne Twister with [mt\_srand()](https://www.php.net/manual/en/function.mt-srand.php).

The incorrect implementation is available for backwards compatibility with
[mt\_srand()](https://www.php.net/manual/en/function.mt-srand.php) prior to PHP 7.1.0.


**Warning**

This feature has been
_DEPRECATED_ as of PHP 8.3.0. Relying on this feature
is highly discouraged.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Frandom.constants%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=random.constants&repo=en&redirect=https://www.php.net/manual/en/random.constants.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google