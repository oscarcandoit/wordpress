---
url: https://www.php.net/manual/en/class.random-randomizer.php
scraped_at: 2025-10-20T02:32:45.743Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The Random\\Randomizer class [¶](https://www.php.net/manual/en/class.random-randomizer.php\#class.random-randomizer)

(PHP 8 >= 8.2.0)

## Introduction [¶](https://www.php.net/manual/en/class.random-randomizer.php\#random-randomizer.intro)

Provides a high-level API to the randomness provided by an [Random\\Engine](https://www.php.net/manual/en/class.random-engine.php).


## Class synopsis [¶](https://www.php.net/manual/en/class.random-randomizer.php\#random-randomizer.synopsis)

finalclass **Random\\Randomizer**
{

/\\* Properties \*/

publicreadonly[Random\\Engine](https://www.php.net/manual/en/class.random-engine.php)[$engine](https://www.php.net/manual/en/class.random-randomizer.php#random-randomizer.props.engine);

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/random-randomizer.construct.php)([?](https://www.php.net/manual/en/language.types.null.php)[Random\\Engine](https://www.php.net/manual/en/class.random-engine.php) `$engine` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**)

public[getBytes](https://www.php.net/manual/en/random-randomizer.getbytes.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$length`): [string](https://www.php.net/manual/en/language.types.string.php)

public[getBytesFromString](https://www.php.net/manual/en/random-randomizer.getbytesfromstring.php)([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$length`): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFloat](https://www.php.net/manual/en/random-randomizer.getfloat.php)([float](https://www.php.net/manual/en/language.types.float.php) `$min`, [float](https://www.php.net/manual/en/language.types.float.php) `$max`, [Random\\IntervalBoundary](https://www.php.net/manual/en/enum.random-intervalboundary.php) `$boundary` = Random\\IntervalBoundary::ClosedOpen): [float](https://www.php.net/manual/en/language.types.float.php)

public[getInt](https://www.php.net/manual/en/random-randomizer.getint.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$min`, [int](https://www.php.net/manual/en/language.types.integer.php) `$max`): [int](https://www.php.net/manual/en/language.types.integer.php)

public[nextFloat](https://www.php.net/manual/en/random-randomizer.nextfloat.php)(): [float](https://www.php.net/manual/en/language.types.float.php)

public[nextInt](https://www.php.net/manual/en/random-randomizer.nextint.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[pickArrayKeys](https://www.php.net/manual/en/random-randomizer.pickarraykeys.php)([array](https://www.php.net/manual/en/language.types.array.php) `$array`, [int](https://www.php.net/manual/en/language.types.integer.php) `$num`): [array](https://www.php.net/manual/en/language.types.array.php)

public[\_\_serialize](https://www.php.net/manual/en/random-randomizer.serialize.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[shuffleArray](https://www.php.net/manual/en/random-randomizer.shufflearray.php)([array](https://www.php.net/manual/en/language.types.array.php) `$array`): [array](https://www.php.net/manual/en/language.types.array.php)

public[shuffleBytes](https://www.php.net/manual/en/random-randomizer.shufflebytes.php)([string](https://www.php.net/manual/en/language.types.string.php) `$bytes`): [string](https://www.php.net/manual/en/language.types.string.php)

public[\_\_unserialize](https://www.php.net/manual/en/random-randomizer.unserialize.php)([array](https://www.php.net/manual/en/language.types.array.php) `$data`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Properties [¶](https://www.php.net/manual/en/class.random-randomizer.php\#random-randomizer.props)

engine

The low-level source of randomness for the [Random\\Randomizer](https://www.php.net/manual/en/class.random-randomizer.php)’s methods.


## Table of Contents [¶](https://www.php.net/manual/en/class.random-randomizer.php\#class.random-randomizer)

- [Random\\Randomizer::\_\_construct](https://www.php.net/manual/en/random-randomizer.construct.php) — Constructs a new Randomizer
- [Random\\Randomizer::getBytes](https://www.php.net/manual/en/random-randomizer.getbytes.php) — Get random bytes
- [Random\\Randomizer::getBytesFromString](https://www.php.net/manual/en/random-randomizer.getbytesfromstring.php) — Get random bytes from a source string
- [Random\\Randomizer::getFloat](https://www.php.net/manual/en/random-randomizer.getfloat.php) — Get a uniformly selected float
- [Random\\Randomizer::getInt](https://www.php.net/manual/en/random-randomizer.getint.php) — Get a uniformly selected integer
- [Random\\Randomizer::nextFloat](https://www.php.net/manual/en/random-randomizer.nextfloat.php) — Get a float from the right-open interval \[0.0, 1.0)\
- [Random\\Randomizer::nextInt](https://www.php.net/manual/en/random-randomizer.nextint.php) — Get a positive integer\
- [Random\\Randomizer::pickArrayKeys](https://www.php.net/manual/en/random-randomizer.pickarraykeys.php) — Select random array keys\
- [Random\\Randomizer::\_\_serialize](https://www.php.net/manual/en/random-randomizer.serialize.php) — Serializes the Randomizer object\
- [Random\\Randomizer::shuffleArray](https://www.php.net/manual/en/random-randomizer.shufflearray.php) — Get a permutation of an array\
- [Random\\Randomizer::shuffleBytes](https://www.php.net/manual/en/random-randomizer.shufflebytes.php) — Get a byte-wise permutation of a string\
- [Random\\Randomizer::\_\_unserialize](https://www.php.net/manual/en/random-randomizer.unserialize.php) — Deserializes the data parameter into a Randomizer object\
\
### Found A Problem?\
\
[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")\
•\
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/random.randomizer.xml)\
•\
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.random-randomizer%0A%0A---)\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=class.random-randomizer&repo=en&redirect=https://www.php.net/manual/en/class.random-randomizer.php)\
\
### User Contributed Notes\
\
There are no user contributed notes for this page.\
\
![To Top](https://www.php.net/images/to-top@2x.png)\
\
`↑` and `↓` to navigate •\
`Enter` to select •\
`Esc` to close\
\
\
Press `Enter` without\
selection to search using Google