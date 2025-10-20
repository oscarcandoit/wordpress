---
url: https://www.php.net/manual/en/intro.pdo.php
scraped_at: 2025-10-20T02:41:56.761Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Introduction [¶](https://www.php.net/manual/en/intro.pdo.php\#intro.pdo)

The `PHP Data Objects` (PDO) extension defines a lightweight, consistent interface
for accessing databases in PHP. Each database driver that
implements the PDO interface can expose database-specific
features as regular extension functions. Note that you cannot
perform any database functions using the PDO extension by
itself; you must use a [database-specific\\
PDO driver](https://www.php.net/manual/en/pdo.drivers.php) to access a database server.


PDO provides a _data-access_ abstraction layer, which
means that, regardless of which database you're using, you use the same
functions to issue queries and fetch data. PDO does
_not_ provide a _database_
abstraction; it doesn't rewrite SQL or emulate missing features. You
should use a full-blown abstraction layer if you need that facility.


PDO ships with PHP.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/pdo/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fintro.pdo%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=intro.pdo&repo=en&redirect=https://www.php.net/manual/en/intro.pdo.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google