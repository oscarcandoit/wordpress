---
url: https://www.php.net/manual/en/class.random-engine.php
scraped_at: 2025-10-20T02:39:05.193Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Random\\Engine interface [¶](https://www.php.net/manual/en/class.random-engine.php\#class.random-engine)

(PHP 8 >= 8.2.0)

## Introduction [¶](https://www.php.net/manual/en/class.random-engine.php\#random-engine.intro)

A **Random\\Engine** provides a low-level source of randomness by
returning random bytes that are consumed by high-level APIs to perform their operations.
The **Random\\Engine** interface allows swapping out the algorithm
used to generate randomness, because each algorithm makes different tradeoffs to fit
specific use-cases. Some algorithms are very fast, but generate lower-quality randomness,
whereas other algorithms are slower, but generate better randomness, up to
cryptographically secure randomness as provided by the [Random\\Engine\\Secure](https://www.php.net/manual/en/class.random-engine-secure.php)
engine.


PHP provides several **Random\\Engine**s out of the box to accomodate
different use-cases. The [Random\\Engine\\Secure](https://www.php.net/manual/en/class.random-engine-secure.php) engine that is
backed by a CSPRNG is the recommended safe default choice, unless
the application requires either reproducible sequences or very high performance.


## Interface synopsis [¶](https://www.php.net/manual/en/class.random-engine.php\#random-engine.synopsis)

interface **Random\\Engine** {

/\\* Methods \*/

public[generate](https://www.php.net/manual/en/random-engine.generate.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.random-engine.php\#class.random-engine)

- [Random\\Engine::generate](https://www.php.net/manual/en/random-engine.generate.php) — Generates randomness

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/random.engine.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.random-engine%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.random-engine&repo=en&redirect=https://www.php.net/manual/en/class.random-engine.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google