---
url: https://www.php.net/manual/en/class.solrclient.php
scraped_at: 2025-10-20T02:31:12.969Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrClient class [¶](https://www.php.net/manual/en/class.solrclient.php\#class.solrclient)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrclient.php\#solrclient.intro)

Used to send requests to a Solr server. Currently, cloning and serialization of SolrClient instances is not supported.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrclient.php\#solrclient.synopsis)

finalclass **SolrClient**
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SEARCH\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.search-servlet-type) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[UPDATE\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.update-servlet-type) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[THREADS\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.threads-servlet-type) = 4;

const[int](https://www.php.net/manual/en/language.types.integer.php)[PING\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.ping-servlet-type) = 8;

const[int](https://www.php.net/manual/en/language.types.integer.php)[TERMS\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.terms-servlet-type) = 16;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SYSTEM\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.system-servlet-type) = 32;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_SEARCH\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-search-servlet) = select;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_UPDATE\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-update-servlet) = update;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_THREADS\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-threads-servlet) = admin/threads;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_PING\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-ping-servlet) = admin/ping;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_TERMS\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-terms-servlet) = terms;

const[string](https://www.php.net/manual/en/language.types.string.php)[DEFAULT\_SYSTEM\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-system-servlet) = admin/system;

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrclient.construct.php)([array](https://www.php.net/manual/en/language.types.array.php) `$clientOptions`)

public[addDocument](https://www.php.net/manual/en/solrclient.adddocument.php)([SolrInputDocument](https://www.php.net/manual/en/class.solrinputdocument.php) `$doc`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$overwrite` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, [int](https://www.php.net/manual/en/language.types.integer.php) `$commitWithin` = 0): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[addDocuments](https://www.php.net/manual/en/solrclient.adddocuments.php)([array](https://www.php.net/manual/en/language.types.array.php) `$docs`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$overwrite` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, [int](https://www.php.net/manual/en/language.types.integer.php) `$commitWithin` = 0): [void](https://www.php.net/manual/en/language.types.void.php)

public[commit](https://www.php.net/manual/en/solrclient.commit.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$softCommit` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$waitSearcher` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$expungeDeletes` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[deleteById](https://www.php.net/manual/en/solrclient.deletebyid.php)([string](https://www.php.net/manual/en/language.types.string.php) `$id`): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[deleteByIds](https://www.php.net/manual/en/solrclient.deletebyids.php)([array](https://www.php.net/manual/en/language.types.array.php) `$ids`): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[deleteByQueries](https://www.php.net/manual/en/solrclient.deletebyqueries.php)([array](https://www.php.net/manual/en/language.types.array.php) `$queries`): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[deleteByQuery](https://www.php.net/manual/en/solrclient.deletebyquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[getById](https://www.php.net/manual/en/solrclient.getbyid.php)([string](https://www.php.net/manual/en/language.types.string.php) `$id`): [SolrQueryResponse](https://www.php.net/manual/en/class.solrqueryresponse.php)

public[getByIds](https://www.php.net/manual/en/solrclient.getbyids.php)([array](https://www.php.net/manual/en/language.types.array.php) `$ids`): [SolrQueryResponse](https://www.php.net/manual/en/class.solrqueryresponse.php)

public[getDebug](https://www.php.net/manual/en/solrclient.getdebug.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getOptions](https://www.php.net/manual/en/solrclient.getoptions.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[optimize](https://www.php.net/manual/en/solrclient.optimize.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxSegments` = 1, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$softCommit` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$waitSearcher` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[ping](https://www.php.net/manual/en/solrclient.ping.php)(): [SolrPingResponse](https://www.php.net/manual/en/class.solrpingresponse.php)

public[query](https://www.php.net/manual/en/solrclient.query.php)([SolrParams](https://www.php.net/manual/en/class.solrparams.php) `$query`): [SolrQueryResponse](https://www.php.net/manual/en/class.solrqueryresponse.php)

public[request](https://www.php.net/manual/en/solrclient.request.php)([string](https://www.php.net/manual/en/language.types.string.php) `$raw_request`): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[rollback](https://www.php.net/manual/en/solrclient.rollback.php)(): [SolrUpdateResponse](https://www.php.net/manual/en/class.solrupdateresponse.php)

public[setResponseWriter](https://www.php.net/manual/en/solrclient.setresponsewriter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$responseWriter`): [void](https://www.php.net/manual/en/language.types.void.php)

public[setServlet](https://www.php.net/manual/en/solrclient.setservlet.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$type`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[system](https://www.php.net/manual/en/solrclient.system.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[threads](https://www.php.net/manual/en/solrclient.threads.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/solrclient.destruct.php)()

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrclient.php\#solrclient.constants)

**`[SolrClient::SEARCH\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.search-servlet-type)`**

Used when updating the search servlet.

**`[SolrClient::UPDATE\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.update-servlet-type)`**

Used when updating the update servlet.

**`[SolrClient::THREADS\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.threads-servlet-type)`**

Used when updating the threads servlet.

**`[SolrClient::PING\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.ping-servlet-type)`**

Used when updating the ping servlet.

**`[SolrClient::TERMS\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.terms-servlet-type)`**

Used when updating the terms servlet.

**`[SolrClient::SYSTEM\_SERVLET\_TYPE](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.system-servlet-type)`**

Used when retrieving system information from the system servlet.

**`[SolrClient::DEFAULT\_SEARCH\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-search-servlet)`**

This is the initial value for the search servlet.

**`[SolrClient::DEFAULT\_UPDATE\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-update-servlet)`**

This is the initial value for the update servlet.

**`[SolrClient::DEFAULT\_THREADS\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-threads-servlet)`**

This is the initial value for the threads servlet.

**`[SolrClient::DEFAULT\_PING\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-ping-servlet)`**

This is the initial value for the ping servlet.

**`[SolrClient::DEFAULT\_TERMS\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-terms-servlet)`**

This is the initial value for the terms servlet used for the TermsComponent

**`[SolrClient::DEFAULT\_SYSTEM\_SERVLET](https://www.php.net/manual/en/class.solrclient.php#solrclient.constants.default-system-servlet)`**

This is the initial value for the system servlet used to obtain Solr Server information

## Table of Contents [¶](https://www.php.net/manual/en/class.solrclient.php\#class.solrclient)

- [SolrClient::addDocument](https://www.php.net/manual/en/solrclient.adddocument.php) — Adds a document to the index
- [SolrClient::addDocuments](https://www.php.net/manual/en/solrclient.adddocuments.php) — Adds a collection of SolrInputDocument instances to the index
- [SolrClient::commit](https://www.php.net/manual/en/solrclient.commit.php) — Finalizes all add/deletes made to the index
- [SolrClient::\_\_construct](https://www.php.net/manual/en/solrclient.construct.php) — Constructor for the SolrClient object
- [SolrClient::deleteById](https://www.php.net/manual/en/solrclient.deletebyid.php) — Delete by Id
- [SolrClient::deleteByIds](https://www.php.net/manual/en/solrclient.deletebyids.php) — Deletes by Ids
- [SolrClient::deleteByQueries](https://www.php.net/manual/en/solrclient.deletebyqueries.php) — Removes all documents matching any of the queries
- [SolrClient::deleteByQuery](https://www.php.net/manual/en/solrclient.deletebyquery.php) — Deletes all documents matching the given query
- [SolrClient::\_\_destruct](https://www.php.net/manual/en/solrclient.destruct.php) — Destructor for SolrClient
- [SolrClient::getById](https://www.php.net/manual/en/solrclient.getbyid.php) — Get Document By Id. Utilizes Solr Realtime Get (RTG)
- [SolrClient::getByIds](https://www.php.net/manual/en/solrclient.getbyids.php) — Get Documents by their Ids. Utilizes Solr Realtime Get (RTG)
- [SolrClient::getDebug](https://www.php.net/manual/en/solrclient.getdebug.php) — Returns the debug data for the last connection attempt
- [SolrClient::getOptions](https://www.php.net/manual/en/solrclient.getoptions.php) — Returns the client options set internally
- [SolrClient::optimize](https://www.php.net/manual/en/solrclient.optimize.php) — Defragments the index
- [SolrClient::ping](https://www.php.net/manual/en/solrclient.ping.php) — Checks if Solr server is still up
- [SolrClient::query](https://www.php.net/manual/en/solrclient.query.php) — Sends a query to the server
- [SolrClient::request](https://www.php.net/manual/en/solrclient.request.php) — Sends a raw update request
- [SolrClient::rollback](https://www.php.net/manual/en/solrclient.rollback.php) — Rollbacks all add/deletes made to the index since the last commit
- [SolrClient::setResponseWriter](https://www.php.net/manual/en/solrclient.setresponsewriter.php) — Sets the response writer used to prepare the response from Solr
- [SolrClient::setServlet](https://www.php.net/manual/en/solrclient.setservlet.php) — Changes the specified servlet type to a new value
- [SolrClient::system](https://www.php.net/manual/en/solrclient.system.php) — Retrieve Solr Server information
- [SolrClient::threads](https://www.php.net/manual/en/solrclient.threads.php) — Checks the threads status

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrclient.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrclient%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrclient&repo=en&redirect=https://www.php.net/manual/en/class.solrclient.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google