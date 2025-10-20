---
url: https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php
scraped_at: 2025-10-20T02:47:31.011Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Random\\Engine\\Xoshiro256StarStar::\_\_construct

(PHP 8 >= 8.2.0)

Random\\Engine\\Xoshiro256StarStar::\_\_construct — Constructs a new xoshiro256\*\* engine

### Description [¶](https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php\#refsect1-random-engine-xoshiro256starstar.construct-description)

public**Random\\Engine\\Xoshiro256StarStar::\_\_construct**([string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$seed` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**)

### Parameters [¶](https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php\#refsect1-random-engine-xoshiro256starstar.construct-parameters)

`seed`

How the internal 256 bit (32 byte) state consisting of four unsigned 64 bit integers is
seeded depends on the type used as the `seed`.


| Type | Description |
| --- | --- |
| [null](https://www.php.net/manual/en/language.types.null.php) | Fills the state with 32 random bytes generated using the CSPRNG. |
| [int](https://www.php.net/manual/en/language.types.integer.php) | Fills the state with four consecutive values generated with the SplitMix64 algorithm<br> that was seeded with `seed` interpreted as an unsigned 64 bit integer. |
| [string](https://www.php.net/manual/en/language.types.string.php) | Fills the state by interpreting a 32 byte [string](https://www.php.net/manual/en/language.types.string.php) as four little-endian unsigned<br> 64 bit integers. |

### Errors/Exceptions [¶](https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php\#refsect1-random-engine-xoshiro256starstar.construct-errors)

- If the length of a [string](https://www.php.net/manual/en/language.types.string.php) `seed` is
not 32 bytes, a [ValueError](https://www.php.net/manual/en/class.valueerror.php) will be thrown.

- If a [string](https://www.php.net/manual/en/language.types.string.php) `seed` consists of
32 NUL bytes ( `"\x00"`), a [ValueError](https://www.php.net/manual/en/class.valueerror.php)
will be thrown.


### Examples [¶](https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php\#refsect1-random-engine-xoshiro256starstar.construct-examples)

**Example #1 **Random\\Engine\\Xoshiro256StarStar::\_\_construct()** example**

`<?php
// Uses a random 256 Bit seed.
$e = new \Random\Engine\Xoshiro256StarStar();
$r = new \Random\Randomizer($e);
?>`

Run code

**Example #2 Deriving a seed from a [string](https://www.php.net/manual/en/language.types.string.php)**

`<?php
$string = "My string seed";
// Hash the string with SHA-256 using binary output to turn the
// $string into a 256 Bit seed. Using the same string will result
// in the same sequence of randomness.
$e = new \Random\Engine\Xoshiro256StarStar(
    hash('sha256', $string, binary: true)
);
echo bin2hex($e->generate()), "\n";
?>`

Run code

The above example will output:

```
6e013453678388c2
```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/random/engine/xoshiro256starstar/construct.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Frandom-engine-xoshiro256starstar.construct%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=random-engine-xoshiro256starstar.construct&repo=en&redirect=https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google