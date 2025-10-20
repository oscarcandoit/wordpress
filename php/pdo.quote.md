---
url: https://www.php.net/manual/en/pdo.quote.php
scraped_at: 2025-10-20T03:01:22.414Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# PDO::quote

(PHP 5 >= 5.1.0, PHP 7, PHP 8, PECL pdo >= 0.2.1)

PDO::quote —
Quotes a string for use in a query


### Description [¶](https://www.php.net/manual/en/pdo.quote.php\#refsect1-pdo.quote-description)

public**PDO::quote**([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [int](https://www.php.net/manual/en/language.types.integer.php) `$type` = PDO::PARAM\_STR): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

**PDO::quote()** places quotes around the input string (if
required) and escapes special characters within the input string, using a
quoting style appropriate to the underlying driver.


If you are using this function to build SQL statements, you are
_strongly_ recommended to use
[PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php) to prepare SQL statements with bound
parameters instead of using **PDO::quote()** to interpolate
user input into an SQL statement. Prepared statements with bound parameters
are not only more portable, more convenient, immune to SQL injection, but
are often much faster to execute than interpolated queries, as both the
server and client side can cache a compiled form of the query.


Not all PDO drivers implement this method (notably PDO\_ODBC). Consider
using prepared statements instead.


**Caution**

# Security: the default character set

The character set must be set either on the server level, or within the
database connection itself (depending on the driver) for it to affect
**PDO::quote()**. See the [driver-specific\\
documentation](https://www.php.net/manual/en/pdo.drivers.php) for more information.


### Parameters [¶](https://www.php.net/manual/en/pdo.quote.php\#refsect1-pdo.quote-parameters)

`string`

The string to be quoted.


`type`

Provides a hint to the type of data for drivers that have alternate quoting
styles. For example **`PDO_PARAM_LOB`** will tell the driver to
escape binary data.


### Return Values [¶](https://www.php.net/manual/en/pdo.quote.php\#refsect1-pdo.quote-returnvalues)

Returns a quoted string that is theoretically safe to pass into an
SQL statement. Returns **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** if the driver does not support quoting in
this way.


### Examples [¶](https://www.php.net/manual/en/pdo.quote.php\#refsect1-pdo.quote-examples)

**Example #1 Quoting a normal string**

`<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');
/* Simple string */
$string = 'Nice';
print "Unquoted string: $string\n";
print "Quoted string: " . $conn->quote($string) . "\n";
?>`

The above example will output:

```
Unquoted string: Nice
Quoted string: 'Nice'
```

**Example #2 Quoting a dangerous string**

`<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');
/* Dangerous string */
$string = 'Naughty \' string';
print "Unquoted string: $string\n";
print "Quoted string:" . $conn->quote($string) . "\n";
?>`

The above example will output:

```
Unquoted string: Naughty ' string
Quoted string: 'Naughty '' string'
```

**Example #3 Quoting a complex string**

`<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');
/* Complex string */
$string = "Co'mpl''ex \"st'\"ring";
print "Unquoted string: $string\n";
print "Quoted string: " . $conn->quote($string) . "\n";
?>`

The above example will output:

```
Unquoted string: Co'mpl''ex "st'"ring
Quoted string: 'Co''mpl''''ex "st''"ring'
```

### See Also [¶](https://www.php.net/manual/en/pdo.quote.php\#refsect1-pdo.quote-seealso)

- [PDO::prepare()](https://www.php.net/manual/en/pdo.prepare.php) \- Prepares a statement for execution and returns a statement object
- [PDOStatement::execute()](https://www.php.net/manual/en/pdostatement.execute.php) \- Executes a prepared statement

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/pdo/quote.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fpdo.quote%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=pdo.quote&repo=en&redirect=https://www.php.net/manual/en/pdo.quote.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google