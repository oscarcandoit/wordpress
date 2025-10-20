---
url: https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html
scraped_at: 2025-10-20T03:07:39.145Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html "Hide Sidebar")

[Previous: Using Collation in INFORMATION_SCHEMA Searches](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-information-schema.html "Previous: Using Collation in INFORMATION_SCHEMA Searches")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Up: Character Sets, Collations, Unicode")[Next: The utf8mb4 Character Set (4-Byte UTF-8 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8mb4.html "Next: The utf8mb4 Character Set (4-Byte UTF-8 Unicode Encoding)")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/charset-unicode.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/charset-unicode.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/charset-unicode.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/charset-unicode.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/charset-unicode.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/charset-unicode.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/charset-unicode.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/charset-unicode.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Character Sets, Collations, Unicode](https://dev.mysql.com/doc/refman/8.0/en/charset.html)  /
Unicode Support


## 12.9 Unicode Support

[12.9.1 The utf8mb4 Character Set (4-Byte UTF-8 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8mb4.html)[12.9.2 The utf8mb3 Character Set (3-Byte UTF-8 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8mb3.html)[12.9.3 The utf8 Character Set (Deprecated alias for utf8mb3)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8.html)[12.9.4 The ucs2 Character Set (UCS-2 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-ucs2.html)[12.9.5 The utf16 Character Set (UTF-16 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf16.html)[12.9.6 The utf16le Character Set (UTF-16LE Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf16le.html)[12.9.7 The utf32 Character Set (UTF-32 Unicode Encoding)](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf32.html)[12.9.8 Converting Between 3-Byte and 4-Byte Unicode Character Sets](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-conversion.html)

The Unicode Standard includes characters from the Basic
Multilingual Plane (BMP) and supplementary characters that lie
outside the BMP. This section describes support for Unicode in
MySQL. For information about the Unicode Standard itself, visit
the [Unicode Consortium\\
website](http://www.unicode.org/).


BMP characters have these characteristics:

- Their code point values are between 0 and 65535 (or
`U+0000` and `U+FFFF`).


- They can be encoded in a variable-length encoding using 8, 16,
or 24 bits (1 to 3 bytes).


- They can be encoded in a fixed-length encoding using 16 bits
(2 bytes).


- They are sufficient for almost all characters in major
languages.


Supplementary characters lie outside the BMP:

- Their code point values are between `U+10000`
and `U+10FFFF`).


- Unicode support for supplementary characters requires
character sets that have a range outside BMP characters and
therefore take more space than BMP characters (up to 4 bytes
per character).


The UTF-8 (Unicode Transformation Format with 8-bit units) method
for encoding Unicode data is implemented according to RFC 3629,
which describes encoding sequences that take from one to four
bytes. The idea of UTF-8 is that various Unicode characters are
encoded using byte sequences of different lengths:

- Basic Latin letters, digits, and punctuation signs use one
byte.


- Most European and Middle East script letters fit into a 2-byte
sequence: extended Latin letters (with tilde, macron, acute,
grave and other accents), Cyrillic, Greek, Armenian, Hebrew,
Arabic, Syriac, and others.


- Korean, Chinese, and Japanese ideographs use 3-byte or 4-byte
sequences.


MySQL supports these Unicode character sets:

- `utf8mb4`: A UTF-8 encoding of the Unicode
character set using one to four bytes per character.


- `utf8mb3`: A UTF-8 encoding of the Unicode
character set using one to three bytes per character. This
character set is deprecated in MySQL 8.0, and you should use
`utf8mb4` instead.


- `utf8`: An alias for
`utf8mb3`. In MySQL 8.0, this alias is
deprecated; use `utf8mb4` instead.
`utf8` is expected in a future release to
become an alias for `utf8mb4`.


- `ucs2`: The UCS-2 encoding of the Unicode
character set using two bytes per character. Deprecated in
MySQL 8.0.28; you should expect support for this character set
to be removed in a future release.


- `utf16`: The UTF-16 encoding for the Unicode
character set using two or four bytes per character. Like
`ucs2` but with an extension for
supplementary characters.


- `utf16le`: The UTF-16LE encoding for the
Unicode character set. Like `utf16` but
little-endian rather than big-endian.


- `utf32`: The UTF-32 encoding for the Unicode
character set using four bytes per character.


Note

The `utf8mb3` character set is deprecated and
you should expect it to be removed in a future MySQL release.
Please use `utf8mb4` instead.
`utf8` is currently an alias for
`utf8mb3`, but it is now deprecated as such,
and `utf8` is expected subsequently to become a
reference to `utf8mb4`. Beginning with MySQL
8.0.28, `utf8mb3` is also displayed in place of
`utf8` in columns of Information Schema tables,
and in the output of SQL `SHOW` statements.


In addition, in MySQL 8.0.30, all collations using the
`utf8_` prefix are renamed using the prefix
`utf8mb3_`.


To avoid ambiguity about the meaning of `utf8`,
consider specifying `utf8mb4` explicitly for
character set references.

[Table 12.2, “Unicode Character Set General Characteristics”](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html#charset-unicode-charset-characteristics "Table 12.2 Unicode Character Set General Characteristics"),
summarizes the general characteristics of Unicode character sets
supported by MySQL.

**Table 12.2 Unicode Character Set General Characteristics**

| Character Set | Supported Characters | Required Storage Per Character |
| --- | --- | --- |
| `utf8mb3`, `utf8` (deprecated) | BMP only | 1, 2, or 3 bytes |
| `ucs2` | BMP only | 2 bytes |
| `utf8mb4` | BMP and supplementary | 1, 2, 3, or 4 bytes |
| `utf16` | BMP and supplementary | 2 or 4 bytes |
| `utf16le` | BMP and supplementary | 2 or 4 bytes |
| `utf32` | BMP and supplementary | 4 bytes |

Characters outside the BMP compare as `REPLACEMENT
      CHARACTER` and convert to `'?'` when
converted to a Unicode character set that supports only BMP
characters ( `utf8mb3` or
`ucs2`).


If you use character sets that support supplementary characters
and thus are “wider” than the BMP-only
`utf8mb3` and `ucs2` character
sets, there are potential incompatibility issues for your
applications; see [Section 12.9.8, “Converting Between 3-Byte and 4-Byte Unicode Character Sets”](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-conversion.html "12.9.8 Converting Between 3-Byte and 4-Byte Unicode Character Sets").
That section also describes how to convert tables from the
(3-byte) `utf8mb3` to the (4-byte)
`utf8mb4`, and what constraints may apply in
doing so.


A similar set of collations is available for most Unicode
character sets. For example, each has a Danish collation, the
names of which are `utf8mb4_danish_ci`,
`utf8mb3_danish_ci` (deprecated),
`utf8_danish_ci` (deprecated),
`ucs2_danish_ci`,
`utf16_danish_ci`, and
`utf32_danish_ci`. The exception is
`utf16le`, which has only two collations. For
information about Unicode collations and their differentiating
properties, including collation properties for supplementary
characters, see [Section 12.10.1, “Unicode Character Sets”](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-sets.html "12.10.1 Unicode Character Sets").


The MySQL implementation of UCS-2, UTF-16, and UTF-32 stores
characters in big-endian byte order and does not use a byte order
mark (BOM) at the beginning of values. Other database systems
might use little-endian byte order or a BOM. In such cases,
conversion of values needs to be performed when transferring data
between those systems and MySQL. The implementation of UTF-16LE is
little-endian.


MySQL uses no BOM for UTF-8 values.


Client applications that communicate with the server using Unicode
should set the client character set accordingly (for example, by
issuing a `SET NAMES 'utf8mb4'` statement). Some
character sets cannot be used as the client character set.
Attempting to use them with [`SET\\
      NAMES`](https://dev.mysql.com/doc/refman/8.0/en/set-names.html "15.7.6.3 SET NAMES Statement") or [`SET CHARACTER\\
      SET`](https://dev.mysql.com/doc/refman/8.0/en/set-character-set.html "15.7.6.2 SET CHARACTER SET Statement") produces an error. See
[Impermissible Client Character Sets](https://dev.mysql.com/doc/refman/8.0/en/charset-connection.html#charset-connection-impermissible-client-charset "Impermissible Client Character Sets").


The following sections provide additional detail on the Unicode
character sets in MySQL.

[PREV](https://dev.mysql.com/doc/refman/8.0/en/charset-collation-information-schema.html "Previous: Using Collation in INFORMATION_SCHEMA Searches") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/charset.html "Up: Character Sets, Collations, Unicode") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode-utf8mb4.html "Next: The utf8mb4 Character Set (4-Byte UTF-8 Unicode Encoding)")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/charset-unicode.html)

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