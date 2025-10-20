---
url: https://www.php.net/manual/en/book.random.php
scraped_at: 2025-10-20T02:35:43.704Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Random Number Generators and Functions Related to Randomness [¶](https://www.php.net/manual/en/book.random.php\#book.random)

- [Introduction](https://www.php.net/manual/en/intro.random.php)
- [Predefined Constants](https://www.php.net/manual/en/random.constants.php)
- [Examples](https://www.php.net/manual/en/random.examples.php)
- [Random Functions](https://www.php.net/manual/en/ref.random.php)
  - [getrandmax](https://www.php.net/manual/en/function.getrandmax.php) — Show largest possible random value
  - [lcg\_value](https://www.php.net/manual/en/function.lcg-value.php) — Combined linear congruential generator
  - [mt\_getrandmax](https://www.php.net/manual/en/function.mt-getrandmax.php) — Show largest possible random value
  - [mt\_rand](https://www.php.net/manual/en/function.mt-rand.php) — Generate a random value via the Mersenne Twister Random Number Generator
  - [mt\_srand](https://www.php.net/manual/en/function.mt-srand.php) — Seeds the Mersenne Twister Random Number Generator
  - [rand](https://www.php.net/manual/en/function.rand.php) — Generate a random integer
  - [random\_bytes](https://www.php.net/manual/en/function.random-bytes.php) — Get cryptographically secure random bytes
  - [random\_int](https://www.php.net/manual/en/function.random-int.php) — Get a cryptographically secure, uniformly selected integer
  - [srand](https://www.php.net/manual/en/function.srand.php) — Seed the random number generator
- [Random\\Randomizer](https://www.php.net/manual/en/class.random-randomizer.php) — The Random\\Randomizer class
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
- [Random\\IntervalBoundary](https://www.php.net/manual/en/enum.random-intervalboundary.php) — The Random\\IntervalBoundary Enum\
- [Random\\Engine](https://www.php.net/manual/en/class.random-engine.php) — The Random\\Engine interface\
  - [Random\\Engine::generate](https://www.php.net/manual/en/random-engine.generate.php) — Generates randomness\
- [Random\\CryptoSafeEngine](https://www.php.net/manual/en/class.random-cryptosafeengine.php) — The Random\\CryptoSafeEngine interface\
- [Random\\Engine\\Secure](https://www.php.net/manual/en/class.random-engine-secure.php) — The Random\\Engine\\Secure class\
  - [Random\\Engine\\Secure::generate](https://www.php.net/manual/en/random-engine-secure.generate.php) — Generate cryptographically secure randomness\
- [Random\\Engine\\Mt19937](https://www.php.net/manual/en/class.random-engine-mt19937.php) — The Random\\Engine\\Mt19937 class\
  - [Random\\Engine\\Mt19937::\_\_construct](https://www.php.net/manual/en/random-engine-mt19937.construct.php) — Constructs a new Mt19937 engine\
  - [Random\\Engine\\Mt19937::\_\_debugInfo](https://www.php.net/manual/en/random-engine-mt19937.debuginfo.php) — Returns the internal state of the engine\
  - [Random\\Engine\\Mt19937::generate](https://www.php.net/manual/en/random-engine-mt19937.generate.php) — Generate 32 bits of randomness\
  - [Random\\Engine\\Mt19937::\_\_serialize](https://www.php.net/manual/en/random-engine-mt19937.serialize.php) — Serializes the Mt19937 object\
  - [Random\\Engine\\Mt19937::\_\_unserialize](https://www.php.net/manual/en/random-engine-mt19937.unserialize.php) — Deserializes the data parameter into a Mt19937 object\
- [Random\\Engine\\PcgOneseq128XslRr64](https://www.php.net/manual/en/class.random-engine-pcgoneseq128xslrr64.php) — The Random\\Engine\\PcgOneseq128XslRr64 class\
  - [Random\\Engine\\PcgOneseq128XslRr64::\_\_construct](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.construct.php) — Constructs a new PCG Oneseq 128 XSL RR 64 engine\
  - [Random\\Engine\\PcgOneseq128XslRr64::\_\_debugInfo](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.debuginfo.php) — Returns the internal state of the engine\
  - [Random\\Engine\\PcgOneseq128XslRr64::generate](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.generate.php) — Generate 64 bits of randomness\
  - [Random\\Engine\\PcgOneseq128XslRr64::jump](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.jump.php) — Efficiently move the engine ahead multiple steps\
  - [Random\\Engine\\PcgOneseq128XslRr64::\_\_serialize](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.serialize.php) — Serializes the PcgOneseq128XslRr64 object\
  - [Random\\Engine\\PcgOneseq128XslRr64::\_\_unserialize](https://www.php.net/manual/en/random-engine-pcgoneseq128xslrr64.unserialize.php) — Deserializes the data parameter into a PcgOneseq128XslRr64 object\
- [Random\\Engine\\Xoshiro256StarStar](https://www.php.net/manual/en/class.random-engine-xoshiro256starstar.php) — The Random\\Engine\\Xoshiro256StarStar class\
  - [Random\\Engine\\Xoshiro256StarStar::\_\_construct](https://www.php.net/manual/en/random-engine-xoshiro256starstar.construct.php) — Constructs a new xoshiro256\*\* engine\
  - [Random\\Engine\\Xoshiro256StarStar::\_\_debugInfo](https://www.php.net/manual/en/random-engine-xoshiro256starstar.debuginfo.php) — Returns the internal state of the engine\
  - [Random\\Engine\\Xoshiro256StarStar::generate](https://www.php.net/manual/en/random-engine-xoshiro256starstar.generate.php) — Generate 64 bits of randomness\
  - [Random\\Engine\\Xoshiro256StarStar::jump](https://www.php.net/manual/en/random-engine-xoshiro256starstar.jump.php) — Efficiently move the engine ahead by 2^128 steps\
  - [Random\\Engine\\Xoshiro256StarStar::jumpLong](https://www.php.net/manual/en/random-engine-xoshiro256starstar.jumplong.php) — Efficiently move the engine ahead by 2^192 steps\
  - [Random\\Engine\\Xoshiro256StarStar::\_\_serialize](https://www.php.net/manual/en/random-engine-xoshiro256starstar.serialize.php) — Serializes the Xoshiro256StarStar object\
  - [Random\\Engine\\Xoshiro256StarStar::\_\_unserialize](https://www.php.net/manual/en/random-engine-xoshiro256starstar.unserialize.php) — Deserializes the data parameter into a Xoshiro256StarStar object\
- [Random\\RandomError](https://www.php.net/manual/en/class.random-randomerror.php) — The Random\\RandomError class\
- [Random\\BrokenRandomEngineError](https://www.php.net/manual/en/class.random-brokenrandomengineerror.php) — The Random\\BrokenRandomEngineError class\
- [Random\\RandomException](https://www.php.net/manual/en/class.random-randomexception.php) — The Random\\RandomException class\
\
### Found A Problem?\
\
[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")\
•\
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/random/book.xml)\
•\
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.random%0A%0A---)\
\
[＋add a note](https://www.php.net/manual/add-note.php?sect=book.random&repo=en&redirect=https://www.php.net/manual/en/book.random.php)\
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