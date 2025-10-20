---
url: https://www.php.net/manual/en/class.solrmodifiableparams.php
scraped_at: 2025-10-20T02:41:58.696Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrModifiableParams class [¶](https://www.php.net/manual/en/class.solrmodifiableparams.php\#class.solrmodifiableparams)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrmodifiableparams.php\#solrmodifiableparams.intro)

Represents a collection of name-value pairs sent to the Solr server during a request.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrmodifiableparams.php\#solrmodifiableparams.synopsis)

class **SolrModifiableParams**extends [SolrParams](https://www.php.net/manual/en/class.solrparams.php)implements [Serializable](https://www.php.net/manual/en/class.serializable.php) {

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrmodifiableparams.construct.php)()

public[\_\_destruct](https://www.php.net/manual/en/solrmodifiableparams.destruct.php)()

/\\* Inherited methods \*/

finalpublic[SolrParams::add](https://www.php.net/manual/en/solrparams.add.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

public[SolrParams::addParam](https://www.php.net/manual/en/solrparams.addparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

finalpublic[SolrParams::get](https://www.php.net/manual/en/solrparams.get.php)([string](https://www.php.net/manual/en/language.types.string.php) `$param_name`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

finalpublic[SolrParams::getParam](https://www.php.net/manual/en/solrparams.getparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$param_name` = ?): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

finalpublic[SolrParams::getParams](https://www.php.net/manual/en/solrparams.getparams.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[SolrParams::getPreparedParams](https://www.php.net/manual/en/solrparams.getpreparedparams.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[SolrParams::serialize](https://www.php.net/manual/en/solrparams.serialize.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[SolrParams::set](https://www.php.net/manual/en/solrparams.set.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [void](https://www.php.net/manual/en/language.types.void.php)

public[SolrParams::setParam](https://www.php.net/manual/en/solrparams.setparam.php)([string](https://www.php.net/manual/en/language.types.string.php) `$name`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrParams](https://www.php.net/manual/en/class.solrparams.php)

finalpublic[SolrParams::toString](https://www.php.net/manual/en/solrparams.tostring.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$url_encode` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[SolrParams::unserialize](https://www.php.net/manual/en/solrparams.unserialize.php)([string](https://www.php.net/manual/en/language.types.string.php) `$serialized`): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Table of Contents [¶](https://www.php.net/manual/en/class.solrmodifiableparams.php\#class.solrmodifiableparams)

- [SolrModifiableParams::\_\_construct](https://www.php.net/manual/en/solrmodifiableparams.construct.php) — Constructor
- [SolrModifiableParams::\_\_destruct](https://www.php.net/manual/en/solrmodifiableparams.destruct.php) — Destructor

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrmodifiableparams.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrmodifiableparams%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrmodifiableparams&repo=en&redirect=https://www.php.net/manual/en/class.solrmodifiableparams.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google