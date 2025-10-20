---
url: https://www.php.net/manual/en/function.stats-cdf-cauchy.php
scraped_at: 2025-10-20T02:31:48.798Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# stats\_cdf\_cauchy

(PECL stats >= 1.0.0)

stats\_cdf\_cauchy — Calculates any one parameter of the Cauchy distribution given values for the others

### Description [¶](https://www.php.net/manual/en/function.stats-cdf-cauchy.php\#refsect1-function.stats-cdf-cauchy-description)

**stats\_cdf\_cauchy**(

[float](https://www.php.net/manual/en/language.types.float.php) `$par1`,

[float](https://www.php.net/manual/en/language.types.float.php) `$par2`,

[float](https://www.php.net/manual/en/language.types.float.php) `$par3`,

[int](https://www.php.net/manual/en/language.types.integer.php) `$which`

): [float](https://www.php.net/manual/en/language.types.float.php)

Returns the cumulative distribution function, its inverse, or one of its parameters,
of the Cauchy distribution. The kind of the return value and parameters
( `par1`, `par2`, and `par3`)
are determined by `which`.


The following table lists the return value and parameters by `which`.
CDF, x, x0, and gamma denotes cumulative distribution function, the value of the random
variable, the location and the scale parameter of the Cauchy distribution, respectively.


| `which` | Return value | `par1` | `par2` | `par3` |
| --- | --- | --- | --- | --- |
| 1 | CDF | x | x0 | gamma |
| 2 | x | CDF | x0 | gamma |
| 3 | x0 | x | CDF | gamma |
| 4 | gamma | x | CDF | x0 |

**Return value and parameters**

### Parameters [¶](https://www.php.net/manual/en/function.stats-cdf-cauchy.php\#refsect1-function.stats-cdf-cauchy-parameters)

`par1`

The first parameter


`par2`

The second parameter


`par3`

The third parameter


`which`

The flag to determine what to be calculated


### Return Values [¶](https://www.php.net/manual/en/function.stats-cdf-cauchy.php\#refsect1-function.stats-cdf-cauchy-returnvalues)

Returns CDF, x, x0, or gamma, determined by `which`.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/stats/functions/stats-cdf-cauchy.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.stats-cdf-cauchy%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.stats-cdf-cauchy&repo=en&redirect=https://www.php.net/manual/en/function.stats-cdf-cauchy.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google