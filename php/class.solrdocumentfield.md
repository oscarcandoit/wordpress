---
url: https://www.php.net/manual/en/class.solrdocumentfield.php
scraped_at: 2025-10-20T02:41:08.227Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrDocumentField class [¶](https://www.php.net/manual/en/class.solrdocumentfield.php\#class.solrdocumentfield)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrdocumentfield.php\#solrdocumentfield.intro)

This represents a field in a Solr document. All its properties are read-only.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrdocumentfield.php\#solrdocumentfield.synopsis)

finalclass **SolrDocumentField**
{

/\\* Properties \*/

publicreadonly[string](https://www.php.net/manual/en/language.types.string.php)[$name](https://www.php.net/manual/en/class.solrdocumentfield.php#solrdocumentfield.props.name);

publicreadonly[float](https://www.php.net/manual/en/language.types.float.php)[$boost](https://www.php.net/manual/en/class.solrdocumentfield.php#solrdocumentfield.props.boost);

publicreadonly[array](https://www.php.net/manual/en/language.types.array.php)[$values](https://www.php.net/manual/en/class.solrdocumentfield.php#solrdocumentfield.props.values);

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrdocumentfield.construct.php)()

public[\_\_destruct](https://www.php.net/manual/en/solrdocumentfield.destruct.php)()

}

## Properties [¶](https://www.php.net/manual/en/class.solrdocumentfield.php\#solrdocumentfield.props)

name

The name of the field.

boost

The boost value for the field

values

An array of values for this field

## Table of Contents [¶](https://www.php.net/manual/en/class.solrdocumentfield.php\#class.solrdocumentfield)

- [SolrDocumentField::\_\_construct](https://www.php.net/manual/en/solrdocumentfield.construct.php) — Constructor
- [SolrDocumentField::\_\_destruct](https://www.php.net/manual/en/solrdocumentfield.destruct.php) — Destructor

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrdocumentfield.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrdocumentfield%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrdocumentfield&repo=en&redirect=https://www.php.net/manual/en/class.solrdocumentfield.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google