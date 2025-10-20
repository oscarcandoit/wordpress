---
url: https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html
scraped_at: 2025-10-20T03:02:32.725Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html "Hide Sidebar")

[Previous: Character Set and Collation of Function Results](https://dev.mysql.com/doc/refman/8.0/en/string-functions-charset.html "Previous: Character Set and Collation of Function Results")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators")[Next: Natural Language Full-Text Searches](https://dev.mysql.com/doc/refman/8.0/en/fulltext-natural-language.html "Next: Natural Language Full-Text Searches")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

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

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/fulltext-search.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/fulltext-search.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/fulltext-search.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/fulltext-search.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/fulltext-search.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/fulltext-search.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/fulltext-search.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/fulltext-search.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)  /
Full-Text Search Functions


## 14.9 Full-Text Search Functions

[14.9.1 Natural Language Full-Text Searches](https://dev.mysql.com/doc/refman/8.0/en/fulltext-natural-language.html)[14.9.2 Boolean Full-Text Searches](https://dev.mysql.com/doc/refman/8.0/en/fulltext-boolean.html)[14.9.3 Full-Text Searches with Query Expansion](https://dev.mysql.com/doc/refman/8.0/en/fulltext-query-expansion.html)[14.9.4 Full-Text Stopwords](https://dev.mysql.com/doc/refman/8.0/en/fulltext-stopwords.html)[14.9.5 Full-Text Restrictions](https://dev.mysql.com/doc/refman/8.0/en/fulltext-restrictions.html)[14.9.6 Fine-Tuning MySQL Full-Text Search](https://dev.mysql.com/doc/refman/8.0/en/fulltext-fine-tuning.html)[14.9.7 Adding a User-Defined Collation for Full-Text Indexing](https://dev.mysql.com/doc/refman/8.0/en/full-text-adding-collation.html)[14.9.8 ngram Full-Text Parser](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-ngram.html)[14.9.9 MeCab Full-Text Parser Plugin](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-mecab.html)

[`MATCH\\
      (col1,col2,...)\\
      AGAINST (expr\\
      [search_modifier])`](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html#function_match)

```sql
search_modifier:
  {
       IN NATURAL LANGUAGE MODE
     | IN NATURAL LANGUAGE MODE WITH QUERY EXPANSION
     | IN BOOLEAN MODE
     | WITH QUERY EXPANSION
  }
```

MySQL has support for full-text indexing and searching:

- A full-text index in MySQL is an index of type
`FULLTEXT`.


- Full-text indexes can be used only with
[`InnoDB`](https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html "Chapter 17 The InnoDB Storage Engine") or
[`MyISAM`](https://dev.mysql.com/doc/refman/8.0/en/myisam-storage-engine.html "18.2 The MyISAM Storage Engine") tables, and can be created
only for [`CHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"),
[`VARCHAR`](https://dev.mysql.com/doc/refman/8.0/en/char.html "13.3.2 The CHAR and VARCHAR Types"), or
[`TEXT`](https://dev.mysql.com/doc/refman/8.0/en/blob.html "13.3.4 The BLOB and TEXT Types") columns.


- MySQL provides a built-in full-text ngram parser that supports
Chinese, Japanese, and Korean (CJK), and an installable MeCab
full-text parser plugin for Japanese. Parsing differences are
outlined in [Section 14.9.8, “ngram Full-Text Parser”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-ngram.html "14.9.8 ngram Full-Text Parser"), and
[Section 14.9.9, “MeCab Full-Text Parser Plugin”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search-mecab.html "14.9.9 MeCab Full-Text Parser Plugin").


- A `FULLTEXT` index definition can be given in
the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "15.1.20 CREATE TABLE Statement") statement when
a table is created, or added later using
[`ALTER TABLE`](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html "15.1.9 ALTER TABLE Statement") or
[`CREATE INDEX`](https://dev.mysql.com/doc/refman/8.0/en/create-index.html "15.1.15 CREATE INDEX Statement").


- For large data sets, it is much faster to load your data into
a table that has no `FULLTEXT` index and then
create the index after that, than to load data into a table
that has an existing `FULLTEXT` index.


Full-text searching is performed using
[`MATCH() AGAINST()`](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html#function_match) syntax.
[`MATCH()`](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html#function_match) takes a comma-separated
list that names the columns to be searched.
`AGAINST` takes a string to search for, and an
optional modifier that indicates what type of search to perform.
The search string must be a string value that is constant during
query evaluation. This rules out, for example, a table column
because that can differ for each row.


Previously, MySQL permitted the use of a rollup column with
`MATCH()`, but queries employing this construct
performed poorly and with unreliable results. (This is due to the
fact that `MATCH()` is not implemented as a
function of its arguments, but rather as a function of the row ID
of the current row in the underlying scan of the base table.) As
of MySQL 8.0.28, MySQL no longer allows such queries; more
specifically, any query matching all of the criteria listed here
is rejected with
[`ER_FULLTEXT_WITH_ROLLUP`](https://dev.mysql.com/doc/mysql-errors/8.0/en/server-error-reference.html#error_er_fulltext_with_rollup):

- `MATCH()` appears in the
`SELECT` list, `GROUP BY`
clause, `HAVING` clause, or `ORDER
            BY` clause of a query block.


- The query block contains a `GROUP BY ... WITH
            ROLLUP` clause.


- The argument of the call to the `MATCH()`
function is one of the grouping columns.


Some examples of such queries are shown here:


```sql
# MATCH() in SELECT list...
SELECT MATCH (a) AGAINST ('abc') FROM t GROUP BY a WITH ROLLUP;
SELECT 1 FROM t GROUP BY a, MATCH (a) AGAINST ('abc') WITH ROLLUP;

# ...in HAVING clause...
SELECT 1 FROM t GROUP BY a WITH ROLLUP HAVING MATCH (a) AGAINST ('abc');

# ...and in ORDER BY clause
SELECT 1 FROM t GROUP BY a WITH ROLLUP ORDER BY MATCH (a) AGAINST ('abc');
```

The use of `MATCH()` with a rollup column in the
`WHERE` clause is permitted.


There are three types of full-text searches:

- A natural language search interprets the search string as a
phrase in natural human language (a phrase in free text).
There are no special operators, with the exception of double
quote (") characters. The stopword list applies. For more
information about stopword lists, see
[Section 14.9.4, “Full-Text Stopwords”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-stopwords.html "14.9.4 Full-Text Stopwords").



Full-text searches are natural language searches if the
`IN NATURAL LANGUAGE MODE` modifier is given
or if no modifier is given. For more information, see
[Section 14.9.1, “Natural Language Full-Text Searches”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-natural-language.html "14.9.1 Natural Language Full-Text Searches").


- A boolean search interprets the search string using the rules
of a special query language. The string contains the words to
search for. It can also contain operators that specify
requirements such that a word must be present or absent in
matching rows, or that it should be weighted higher or lower
than usual. Certain common words (stopwords) are omitted from
the search index and do not match if present in the search
string. The `IN BOOLEAN MODE` modifier
specifies a boolean search. For more information, see
[Section 14.9.2, “Boolean Full-Text Searches”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-boolean.html "14.9.2 Boolean Full-Text Searches").


- A query expansion search is a modification of a natural
language search. The search string is used to perform a
natural language search. Then words from the most relevant
rows returned by the search are added to the search string and
the search is done again. The query returns the rows from the
second search. The `IN NATURAL LANGUAGE MODE WITH
            QUERY EXPANSION` or `WITH QUERY
            EXPANSION` modifier specifies a query expansion
search. For more information, see
[Section 14.9.3, “Full-Text Searches with Query Expansion”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-query-expansion.html "14.9.3 Full-Text Searches with Query Expansion").


For information about `FULLTEXT` query
performance, see [Section 10.3.5, “Column Indexes”](https://dev.mysql.com/doc/refman/8.0/en/column-indexes.html "10.3.5 Column Indexes").


For more information about `InnoDB` `FULLTEXT` indexes, see
[Section 17.6.2.4, “InnoDB Full-Text Indexes”](https://dev.mysql.com/doc/refman/8.0/en/innodb-fulltext-index.html "17.6.2.4 InnoDB Full-Text Indexes").


Constraints on full-text searching are listed in
[Section 14.9.5, “Full-Text Restrictions”](https://dev.mysql.com/doc/refman/8.0/en/fulltext-restrictions.html "14.9.5 Full-Text Restrictions").


The [**myisam\_ftdump**](https://dev.mysql.com/doc/refman/8.0/en/myisam-ftdump.html "6.6.3 myisam_ftdump — Display Full-Text Index information") utility dumps the contents of
a `MyISAM` full-text index. This may be helpful
for debugging full-text queries. See
[Section 6.6.3, “myisam\_ftdump — Display Full-Text Index information”](https://dev.mysql.com/doc/refman/8.0/en/myisam-ftdump.html "6.6.3 myisam_ftdump — Display Full-Text Index information").

[PREV](https://dev.mysql.com/doc/refman/8.0/en/string-functions-charset.html "Previous: Character Set and Collation of Function Results") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Up: Functions and Operators") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/fulltext-natural-language.html "Next: Natural Language Full-Text Searches")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

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

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/fulltext-search.html)

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