---
url: https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html
scraped_at: 2025-10-20T03:07:42.875Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html "Hide Sidebar")

[Previous: Specifying Character Sets and Collations](https://dev.mysql.com/doc/refman/8.0/en/charset-syntax.html "Previous: Specifying Character Sets and Collations")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Specifying Character Sets and Collations](https://dev.mysql.com/doc/refman/8.0/en/charset-syntax.html "Up: Specifying Character Sets and Collations")[Next: Server Character Set and Collation](https://dev.mysql.com/doc/refman/8.0/en/charset-server.html "Next: Server Character Set and Collation")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/charset-collation-names.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/charset-collation-names.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/charset-collation-names.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/charset-collation-names.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/charset-collation-names.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/charset-collation-names.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/charset-collation-names.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/charset-collation-names.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)  / [Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html)  /
[Specifying Character Sets and Collations](https://dev.mysql.com/doc/refman/8.0/en/charset-syntax.html)  /

Collation Naming Conventions


### 12.3.1 Collation Naming Conventions

MySQL collation names follow these conventions:

- A collation name starts with the name of the character set
with which it is associated, generally followed by one or
more suffixes indicating other collation characteristics.
For example, `utf8mb4_0900_ai_ci` and
`latin1_swedish_ci` are collations for the
`utf8mb4` and `latin1`
character sets, respectively. The `binary`
character set has a single collation, also named
`binary`, with no suffixes.


- A language-specific collation includes a locale code or
language name. For example,
`utf8mb4_tr_0900_ai_ci` and
`utf8mb4_hu_0900_ai_ci` sort characters for
the `utf8mb4` character set using the rules
of Turkish and Hungarian, respectively.
`utf8mb4_turkish_ci` and
`utf8mb4_hungarian_ci` are similar but
based on a less recent version of the Unicode Collation
Algorithm.


- Collation suffixes indicate whether a collation is
case-sensitive, accent-sensitive, or kana-sensitive (or some
combination thereof), or binary. The following table shows
the suffixes used to indicate these characteristics.




**Table 12.1 Collation Suffix Meanings**






| Suffix | Meaning |
| --- | --- |
| `_ai` | Accent-insensitive |
| `_as` | Accent-sensitive |
| `_ci` | Case-insensitive |
| `_cs` | Case-sensitive |
| `_ks` | Kana-sensitive |
| `_bin` | Binary |








For nonbinary collation names that do not specify accent
sensitivity, it is determined by case sensitivity. If a
collation name does not contain `_ai` or
`_as`, `_ci` in the name
implies `_ai` and `_cs` in
the name implies `_as`. For example,
`latin1_general_ci` is explicitly
case-insensitive and implicitly accent-insensitive,
`latin1_general_cs` is explicitly
case-sensitive and implicitly accent-sensitive, and
`utf8mb4_0900_ai_ci` is explicitly
case-insensitive and accent-insensitive.



For Japanese collations, the `_ks` suffix
indicates that a collation is kana-sensitive; that is, it
distinguishes Katakana characters from Hiragana characters.
Japanese collations without the `_ks`
suffix are not kana-sensitive and treat Katakana and
Hiragana characters equal for sorting.



For the `binary` collation of the
`binary` character set, comparisons are
based on numeric byte values. For the
`_bin` collation of a nonbinary character
set, comparisons are based on numeric character code values,
which differ from byte values for multibyte characters. For
information about the differences between the
`binary` collation of the
`binary` character set and the
`_bin` collations of nonbinary character
sets, see [Section 12.8.5, “The binary Collation Compared to \_bin Collations”](https://dev.mysql.com/doc/refman/8.0/en/charset-binary-collations.html "12.8.5 The binary Collation Compared to _bin Collations").


- Collation names for Unicode character sets may include a
version number to indicate the version of the Unicode
Collation Algorithm (UCA) on which the collation is based.
UCA-based collations without a version number in the name
use the version-4.0.0 UCA weight keys. For example:




- `utf8mb4_0900_ai_ci` is based on UCA
9.0.0 weight keys
( [http://www.unicode.org/Public/UCA/9.0.0/allkeys.txt](http://www.unicode.org/Public/UCA/9.0.0/allkeys.txt)).


- `utf8mb4_unicode_520_ci` is based on
UCA 5.2.0 weight keys
( [http://www.unicode.org/Public/UCA/5.2.0/allkeys.txt](http://www.unicode.org/Public/UCA/5.2.0/allkeys.txt)).


- `utf8mb4_unicode_ci` (with no version
named) is based on UCA 4.0.0 weight keys
( [http://www.unicode.org/Public/UCA/4.0.0/allkeys-4.0.0.txt](http://www.unicode.org/Public/UCA/4.0.0/allkeys-4.0.0.txt)).


- For Unicode character sets, the
`xxx_general_mysql500_ci`
collations preserve the pre-5.1.24 ordering of the original
`xxx_general_ci`
collations and permit upgrades for tables created before
MySQL 5.1.24 (Bug #27877).


[PREV](https://dev.mysql.com/doc/refman/8.0/en/charset-syntax.html "Previous: Specifying Character Sets and Collations") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/charset-syntax.html "Up: Specifying Character Sets and Collations") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/charset-server.html "Next: Server Character Set and Collation")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-names.html)

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