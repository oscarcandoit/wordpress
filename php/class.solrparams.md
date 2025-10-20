---
url: https://www.php.net/manual/en/class.solrparams.php
scraped_at: 2025-10-20T02:42:50.316Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrParams class [¶](https://www.php.net/manual/en/class.solrparams.php\#class.solrparams)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrparams.php\#solrparams.intro)

Represents a collection of name-value pairs sent to the Solr server during a request.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrparams.php\#solrparams.synopsis)

abstractclass **SolrParams**implements [Serializable](https://www.php.net/manual/en/class.serializable.php) {

/\\* Methods \*/

finalpublic[add](https://www.php.net/manual/en/solrparams.add.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

public[addParam](https://www.php.net/manual/en/solrparams.addparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

finalpublic[get](https://www.php.net/manual/en/solrparams.get.php)([string](https://www.php.net/manual/en/language.types.string.php) `$param_name`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

finalpublic[getParam](https://www.php.net/manual/en/solrparams.getparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$param_name` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

finalpublic[getParams](https://www.php.net/manual/en/solrparams.getparams.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[getPreparedParams](https://www.php.net/manual/en/solrparams.getpreparedparams.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[serialize](https://www.php.net/manual/en/solrparams.serialize.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[set](https://www.php.net/manual/en/solrparams.set.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setParam](https://www.php.net/manual/en/solrparams.setparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

finalpublic[toString](https://www.php.net/manual/en/solrparams.tostring.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$url_encode` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[unserialize](https://www.php.net/manual/en/solrparams.unserialize.php)([string](https://www.php.net/manual/en/language.types.string.php) `$serialized`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.solrparams.php\#class.solrparams)

- [SolrParams::add](https://www.php.net/manual/en/solrparams.add.php) — Alias of SolrParams::addParam
- [SolrParams::addParam](https://www.php.net/manual/en/solrparams.addparam.php) — Adds a parameter to the object
- [SolrParams::get](https://www.php.net/manual/en/solrparams.get.php) — Alias of SolrParams::getParam
- [SolrParams::getParam](https://www.php.net/manual/en/solrparams.getparam.php) — Returns a parameter value
- [SolrParams::getParams](https://www.php.net/manual/en/solrparams.getparams.php) — Returns an array of non URL-encoded parameters
- [SolrParams::getPreparedParams](https://www.php.net/manual/en/solrparams.getpreparedparams.php) — Returns an array of URL-encoded parameters
- [SolrParams::serialize](https://www.php.net/manual/en/solrparams.serialize.php) — Used for custom serialization
- [SolrParams::set](https://www.php.net/manual/en/solrparams.set.php) — Alias of SolrParams::setParam
- [SolrParams::setParam](https://www.php.net/manual/en/solrparams.setparam.php) — Sets the parameter to the specified value
- [SolrParams::toString](https://www.php.net/manual/en/solrparams.tostring.php) — Returns all the name-value pair parameters in the object
- [SolrParams::unserialize](https://www.php.net/manual/en/solrparams.unserialize.php) — Used for custom serialization

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrparams.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrparams%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrparams&repo=en&redirect=https://www.php.net/manual/en/class.solrparams.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google