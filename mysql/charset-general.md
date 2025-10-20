---
url: https://dev.mysql.com/doc/refman/8.0/en/charset-general.html
scraped_at: 2025-10-20T03:07:34.638Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html "Hide Sidebar")

[Previous: Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Previous: Character Sets, Collations, Unicode")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Up: Character Sets, Collations, Unicode")[Next: Character Sets and Collations in MySQL](https://dev.mysql.com/doc/refman/8.0/en/charset-mysql.html "Next: Character Sets and Collations in MySQL")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/charset-general.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/charset-general.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/charset-general.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/charset-general.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/charset-general.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/charset-general.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/charset-general.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/charset-general.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html)  /
Character Sets and Collations in General


## 12.1 Character Sets and Collations in General

A character set is a set of
symbols and encodings. A
collation is a set of rules
for comparing characters in a character set. Let's make the
distinction clear with an example of an imaginary character set.


Suppose that we have an alphabet with four letters:
`A`, `B`, `a`,
`b`. We give each letter a number:
`A` = 0, `B` = 1,
`a` = 2, `b` = 3\. The letter
`A` is a symbol, the number 0 is the
_encoding_ for `A`, and the
combination of all four letters and their encodings is a
_character set_.


Suppose that we want to compare two string values,
`A` and `B`. The simplest way to
do this is to look at the encodings: 0 for `A`
and 1 for `B`. Because 0 is less than 1, we say
`A` is less than `B`. What we've
just done is apply a collation to our character set. The collation
is a set of rules (only one rule in this case): “compare the
encodings.” We call this simplest of all possible
collations a binary
collation.


But what if we want to say that the lowercase and uppercase
letters are equivalent? Then we would have at least two rules: (1)
treat the lowercase letters `a` and
`b` as equivalent to `A` and
`B`; (2) then compare the encodings. We call this
a case-insensitive
collation. It is a little more complex than a binary collation.


In real life, most character sets have many characters: not just
`A` and `B` but whole alphabets,
sometimes multiple alphabets or eastern writing systems with
thousands of characters, along with many special symbols and
punctuation marks. Also in real life, most collations have many
rules, not just for whether to distinguish lettercase, but also
for whether to distinguish accents (an “accent” is a
mark attached to a character as in German `Ö`),
and for multiple-character mappings (such as the rule that
`Ö` = `OE` in one of the two
German collations).


MySQL can do these things for you:

- Store strings using a variety of character sets.


- Compare strings using a variety of collations.


- Mix strings with different character sets or collations in the
same server, the same database, or even the same table.


- Enable specification of character set and collation at any
level.


To use these features effectively, you must know what character
sets and collations are available, how to change the defaults, and
how they affect the behavior of string operators and functions.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Previous: Character Sets, Collations, Unicode") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Up: Character Sets, Collations, Unicode") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/charset-mysql.html "Next: Character Sets and Collations in MySQL")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-general.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)