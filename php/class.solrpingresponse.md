---
url: https://www.php.net/manual/en/class.solrpingresponse.php
scraped_at: 2025-10-20T02:34:08.176Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrPingResponse class [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#class.solrpingresponse)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#solrpingresponse.intro)

Represents a response to a ping request to the server


## Class synopsis [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#solrpingresponse.synopsis)

finalclass **SolrPingResponse**extends [SolrResponse](https://www.php.net/manual/en/class.solrresponse.php)
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[PARSE\_SOLR\_OBJ](https://www.php.net/manual/en/class.solrpingresponse.php#solrpingresponse.constants.parse-solr-obj) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[PARSE\_SOLR\_DOC](https://www.php.net/manual/en/class.solrpingresponse.php#solrpingresponse.constants.parse-solr-doc) = 1;

/\\* Properties \*/

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrpingresponse.construct.php)()

public[getResponse](https://www.php.net/manual/en/solrpingresponse.getresponse.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[\_\_destruct](https://www.php.net/manual/en/solrpingresponse.destruct.php)()

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

## Properties [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#solrpingresponse.props)

http\_status

The http status of the response.

parser\_mode

Whether to parse the solr documents as SolrObject or SolrDocument instances.

success

Was there an error during the request

http\_status\_message

Detailed message on http status

http\_request\_url

The request URL

http\_raw\_request\_headers

A string of raw headers sent during the request

http\_raw\_request

The raw request sent to the server

http\_raw\_response\_headers

Response headers from the Solr server

http\_raw\_response

The response message from the server

http\_digested\_response

The response in PHP serialized format.

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#solrpingresponse.constants)

## SolrPingResponse Class Constants [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#solrpingresponse.constants.types)

**`[SolrPingResponse::PARSE\_SOLR\_OBJ](https://www.php.net/manual/en/class.solrpingresponse.php#solrpingresponse.constants.parse-solr-obj)`**

Documents should be parsed as SolrObject instances

**`[SolrPingResponse::PARSE\_SOLR\_DOC](https://www.php.net/manual/en/class.solrpingresponse.php#solrpingresponse.constants.parse-solr-doc)`**

Documents should be parsed as SolrDocument instances.

## Table of Contents [¶](https://www.php.net/manual/en/class.solrpingresponse.php\#class.solrpingresponse)

- [SolrPingResponse::\_\_construct](https://www.php.net/manual/en/solrpingresponse.construct.php) — Constructor
- [SolrPingResponse::\_\_destruct](https://www.php.net/manual/en/solrpingresponse.destruct.php) — Destructor
- [SolrPingResponse::getResponse](https://www.php.net/manual/en/solrpingresponse.getresponse.php) — Returns the response from the server

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrpingresponse.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrpingresponse%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrpingresponse&repo=en&redirect=https://www.php.net/manual/en/class.solrpingresponse.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google