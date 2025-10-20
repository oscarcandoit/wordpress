---
url: https://www.php.net/manual/en/class.solrgenericresponse.php
scraped_at: 2025-10-20T02:41:05.974Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrGenericResponse class [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#class.solrgenericresponse)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#solrgenericresponse.intro)

Represents a response from the solr server.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#solrgenericresponse.synopsis)

finalclass **SolrGenericResponse**extends [SolrResponse](https://www.php.net/manual/en/class.solrresponse.php)
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[PARSE\_SOLR\_OBJ](https://www.php.net/manual/en/class.solrgenericresponse.php#solrgenericresponse.constants.parse-solr-obj) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[PARSE\_SOLR\_DOC](https://www.php.net/manual/en/class.solrgenericresponse.php#solrgenericresponse.constants.parse-solr-doc) = 1;

/\\* Inherited properties \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrResponse::PARSE\_SOLR\_OBJ](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.constants.parse-solr-obj) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrResponse::PARSE\_SOLR\_DOC](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.constants.parse-solr-doc) = 1;

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$http\_status](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-status);

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$parser\_mode](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.parser-mode);

protected[bool](https://www.php.net/manual/en/language.types.boolean.php)[$success](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.success);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_status\_message](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-status-message);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_request\_url](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-request-url);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_raw\_request\_headers](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-raw-request-headers);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_raw\_request](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-raw-request);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_raw\_response\_headers](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-raw-response-headers);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_raw\_response](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-raw-response);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$http\_digested\_response](https://www.php.net/manual/en/class.solrresponse.php#solrresponse.props.http-digested-response);

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrgenericresponse.construct.php)()

public[\_\_destruct](https://www.php.net/manual/en/solrgenericresponse.destruct.php)()

/\\* Inherited methods \*/

public[SolrResponse::getDigestedResponse](https://www.php.net/manual/en/solrresponse.getdigestedresponse.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getHttpStatus](https://www.php.net/manual/en/solrresponse.gethttpstatus.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrResponse::getHttpStatusMessage](https://www.php.net/manual/en/solrresponse.gethttpstatusmessage.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getRawRequest](https://www.php.net/manual/en/solrresponse.getrawrequest.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getRawRequestHeaders](https://www.php.net/manual/en/solrresponse.getrawrequestheaders.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getRawResponse](https://www.php.net/manual/en/solrresponse.getrawresponse.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getRawResponseHeaders](https://www.php.net/manual/en/solrresponse.getrawresponseheaders.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getRequestUrl](https://www.php.net/manual/en/solrresponse.getrequesturl.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrResponse::getResponse](https://www.php.net/manual/en/solrresponse.getresponse.php)(): [SolrObject](https://www.php.net/manual/en/class.solrobject.php)

public[SolrResponse::setParseMode](https://www.php.net/manual/en/solrresponse.setparsemode.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$parser_mode` = 0): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrResponse::success](https://www.php.net/manual/en/solrresponse.success.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#solrgenericresponse.constants)

## SolrGenericResponse Class constants [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#solrgenericresponse.constants.types)

**`[SolrGenericResponse::PARSE\_SOLR\_OBJ](https://www.php.net/manual/en/class.solrgenericresponse.php#solrgenericresponse.constants.parse-solr-obj)`**

Documents should be parsed as SolrObject instances

**`[SolrGenericResponse::PARSE\_SOLR\_DOC](https://www.php.net/manual/en/class.solrgenericresponse.php#solrgenericresponse.constants.parse-solr-doc)`**

Documents should be parsed as SolrDocument instances.

## Table of Contents [¶](https://www.php.net/manual/en/class.solrgenericresponse.php\#class.solrgenericresponse)

- [SolrGenericResponse::\_\_construct](https://www.php.net/manual/en/solrgenericresponse.construct.php) — Constructor
- [SolrGenericResponse::\_\_destruct](https://www.php.net/manual/en/solrgenericresponse.destruct.php) — Destructor

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrgenericresponse.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrgenericresponse%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrgenericresponse&repo=en&redirect=https://www.php.net/manual/en/class.solrgenericresponse.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google