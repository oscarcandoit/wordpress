---
url: https://www.php.net/manual/en/class.solrquery.php
scraped_at: 2025-10-20T02:39:07.701Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrQuery class [¶](https://www.php.net/manual/en/class.solrquery.php\#class.solrquery)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrquery.php\#solrquery.intro)

Represents a collection of name-value pairs sent to the Solr server during a request.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrquery.php\#solrquery.synopsis)

class **SolrQuery**extends [SolrModifiableParams](https://www.php.net/manual/en/class.solrmodifiableparams.php)implements [Serializable](https://www.php.net/manual/en/class.serializable.php) {

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[ORDER\_ASC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-asc) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[ORDER\_DESC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-desc) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[FACET\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-index) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[FACET\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-count) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[TERMS\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-index) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[TERMS\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-count) = 1;

/\\* Properties \*/

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrquery.construct.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q` = ?)

public[addExpandFilterQuery](https://www.php.net/manual/en/solrquery.addexpandfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addExpandSortField](https://www.php.net/manual/en/solrquery.addexpandsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$order` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addFacetDateField](https://www.php.net/manual/en/solrquery.addfacetdatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$dateField`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addFacetDateOther](https://www.php.net/manual/en/solrquery.addfacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addFacetField](https://www.php.net/manual/en/solrquery.addfacetfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addFacetQuery](https://www.php.net/manual/en/solrquery.addfacetquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$facetQuery`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addField](https://www.php.net/manual/en/solrquery.addfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addFilterQuery](https://www.php.net/manual/en/solrquery.addfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addGroupField](https://www.php.net/manual/en/solrquery.addgroupfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addGroupFunction](https://www.php.net/manual/en/solrquery.addgroupfunction.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addGroupQuery](https://www.php.net/manual/en/solrquery.addgroupquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addGroupSortField](https://www.php.net/manual/en/solrquery.addgroupsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [int](https://www.php.net/manual/en/language.types.integer.php) `$order` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addHighlightField](https://www.php.net/manual/en/solrquery.addhighlightfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addMltField](https://www.php.net/manual/en/solrquery.addmltfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addMltQueryField](https://www.php.net/manual/en/solrquery.addmltqueryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [float](https://www.php.net/manual/en/language.types.float.php) `$boost`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addSortField](https://www.php.net/manual/en/solrquery.addsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [int](https://www.php.net/manual/en/language.types.integer.php) `$order` = SolrQuery::ORDER\_DESC): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addStatsFacet](https://www.php.net/manual/en/solrquery.addstatsfacet.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[addStatsField](https://www.php.net/manual/en/solrquery.addstatsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[collapse](https://www.php.net/manual/en/solrquery.collapse.php)([SolrCollapseFunction](https://www.php.net/manual/en/class.solrcollapsefunction.php) `$collapseFunction`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[getExpand](https://www.php.net/manual/en/solrquery.getexpand.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getExpandFilterQueries](https://www.php.net/manual/en/solrquery.getexpandfilterqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getExpandQuery](https://www.php.net/manual/en/solrquery.getexpandquery.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getExpandRows](https://www.php.net/manual/en/solrquery.getexpandrows.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getExpandSortFields](https://www.php.net/manual/en/solrquery.getexpandsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFacet](https://www.php.net/manual/en/solrquery.getfacet.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getFacetDateEnd](https://www.php.net/manual/en/solrquery.getfacetdateend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetDateFields](https://www.php.net/manual/en/solrquery.getfacetdatefields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFacetDateGap](https://www.php.net/manual/en/solrquery.getfacetdategap.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetDateHardEnd](https://www.php.net/manual/en/solrquery.getfacetdatehardend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetDateOther](https://www.php.net/manual/en/solrquery.getfacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFacetDateStart](https://www.php.net/manual/en/solrquery.getfacetdatestart.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetFields](https://www.php.net/manual/en/solrquery.getfacetfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFacetLimit](https://www.php.net/manual/en/solrquery.getfacetlimit.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getFacetMethod](https://www.php.net/manual/en/solrquery.getfacetmethod.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetMinCount](https://www.php.net/manual/en/solrquery.getfacetmincount.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getFacetMissing](https://www.php.net/manual/en/solrquery.getfacetmissing.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getFacetOffset](https://www.php.net/manual/en/solrquery.getfacetoffset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getFacetPrefix](https://www.php.net/manual/en/solrquery.getfacetprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getFacetQueries](https://www.php.net/manual/en/solrquery.getfacetqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFacetSort](https://www.php.net/manual/en/solrquery.getfacetsort.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getFields](https://www.php.net/manual/en/solrquery.getfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getFilterQueries](https://www.php.net/manual/en/solrquery.getfilterqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getGroup](https://www.php.net/manual/en/solrquery.getgroup.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getGroupCachePercent](https://www.php.net/manual/en/solrquery.getgroupcachepercent.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getGroupFacet](https://www.php.net/manual/en/solrquery.getgroupfacet.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getGroupFields](https://www.php.net/manual/en/solrquery.getgroupfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getGroupFormat](https://www.php.net/manual/en/solrquery.getgroupformat.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getGroupFunctions](https://www.php.net/manual/en/solrquery.getgroupfunctions.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getGroupLimit](https://www.php.net/manual/en/solrquery.getgrouplimit.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getGroupMain](https://www.php.net/manual/en/solrquery.getgroupmain.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getGroupNGroups](https://www.php.net/manual/en/solrquery.getgroupngroups.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getGroupOffset](https://www.php.net/manual/en/solrquery.getgroupoffset.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getGroupQueries](https://www.php.net/manual/en/solrquery.getgroupqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getGroupSortFields](https://www.php.net/manual/en/solrquery.getgroupsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getGroupTruncate](https://www.php.net/manual/en/solrquery.getgrouptruncate.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getHighlight](https://www.php.net/manual/en/solrquery.gethighlight.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getHighlightAlternateField](https://www.php.net/manual/en/solrquery.gethighlightalternatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightFields](https://www.php.net/manual/en/solrquery.gethighlightfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getHighlightFormatter](https://www.php.net/manual/en/solrquery.gethighlightformatter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightFragmenter](https://www.php.net/manual/en/solrquery.gethighlightfragmenter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightFragsize](https://www.php.net/manual/en/solrquery.gethighlightfragsize.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.gethighlighthighlightmultiterm.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.gethighlightmaxalternatefieldlength.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightmaxanalyzedchars.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.gethighlightmergecontiguous.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getHighlightQuery](https://www.php.net/manual/en/solrquery.gethighlightquery.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightregexmaxanalyzedchars.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getHighlightRegexPattern](https://www.php.net/manual/en/solrquery.gethighlightregexpattern.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightRegexSlop](https://www.php.net/manual/en/solrquery.gethighlightregexslop.php)(): [float](https://www.php.net/manual/en/language.types.float.php)

public[getHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.gethighlightrequirefieldmatch.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getHighlightSimplePost](https://www.php.net/manual/en/solrquery.gethighlightsimplepost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightSimplePre](https://www.php.net/manual/en/solrquery.gethighlightsimplepre.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[getHighlightSnippets](https://www.php.net/manual/en/solrquery.gethighlightsnippets.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.gethighlightusephrasehighlighter.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getMlt](https://www.php.net/manual/en/solrquery.getmlt.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getMltBoost](https://www.php.net/manual/en/solrquery.getmltboost.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getMltCount](https://www.php.net/manual/en/solrquery.getmltcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltFields](https://www.php.net/manual/en/solrquery.getmltfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.getmltmaxnumqueryterms.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltMaxNumTokens](https://www.php.net/manual/en/solrquery.getmltmaxnumtokens.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltMaxWordLength](https://www.php.net/manual/en/solrquery.getmltmaxwordlength.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltMinDocFrequency](https://www.php.net/manual/en/solrquery.getmltmindocfrequency.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltMinTermFrequency](https://www.php.net/manual/en/solrquery.getmltmintermfrequency.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltMinWordLength](https://www.php.net/manual/en/solrquery.getmltminwordlength.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getMltQueryFields](https://www.php.net/manual/en/solrquery.getmltqueryfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getQuery](https://www.php.net/manual/en/solrquery.getquery.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getRows](https://www.php.net/manual/en/solrquery.getrows.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getSortFields](https://www.php.net/manual/en/solrquery.getsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getStart](https://www.php.net/manual/en/solrquery.getstart.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getStats](https://www.php.net/manual/en/solrquery.getstats.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getStatsFacets](https://www.php.net/manual/en/solrquery.getstatsfacets.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getStatsFields](https://www.php.net/manual/en/solrquery.getstatsfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getTerms](https://www.php.net/manual/en/solrquery.getterms.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getTermsField](https://www.php.net/manual/en/solrquery.gettermsfield.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.gettermsincludelowerbound.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.gettermsincludeupperbound.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getTermsLimit](https://www.php.net/manual/en/solrquery.gettermslimit.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getTermsLowerBound](https://www.php.net/manual/en/solrquery.gettermslowerbound.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getTermsMaxCount](https://www.php.net/manual/en/solrquery.gettermsmaxcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getTermsMinCount](https://www.php.net/manual/en/solrquery.gettermsmincount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getTermsPrefix](https://www.php.net/manual/en/solrquery.gettermsprefix.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getTermsReturnRaw](https://www.php.net/manual/en/solrquery.gettermsreturnraw.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getTermsSort](https://www.php.net/manual/en/solrquery.gettermssort.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getTermsUpperBound](https://www.php.net/manual/en/solrquery.gettermsupperbound.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getTimeAllowed](https://www.php.net/manual/en/solrquery.gettimeallowed.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[removeExpandFilterQuery](https://www.php.net/manual/en/solrquery.removeexpandfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeExpandSortField](https://www.php.net/manual/en/solrquery.removeexpandsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeFacetDateField](https://www.php.net/manual/en/solrquery.removefacetdatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeFacetDateOther](https://www.php.net/manual/en/solrquery.removefacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeFacetField](https://www.php.net/manual/en/solrquery.removefacetfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeFacetQuery](https://www.php.net/manual/en/solrquery.removefacetquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeField](https://www.php.net/manual/en/solrquery.removefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeFilterQuery](https://www.php.net/manual/en/solrquery.removefilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeHighlightField](https://www.php.net/manual/en/solrquery.removehighlightfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeMltField](https://www.php.net/manual/en/solrquery.removemltfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeMltQueryField](https://www.php.net/manual/en/solrquery.removemltqueryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$queryField`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeSortField](https://www.php.net/manual/en/solrquery.removesortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeStatsFacet](https://www.php.net/manual/en/solrquery.removestatsfacet.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[removeStatsField](https://www.php.net/manual/en/solrquery.removestatsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setEchoHandler](https://www.php.net/manual/en/solrquery.setechohandler.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setEchoParams](https://www.php.net/manual/en/solrquery.setechoparams.php)([string](https://www.php.net/manual/en/language.types.string.php) `$type`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setExpand](https://www.php.net/manual/en/solrquery.setexpand.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setExpandQuery](https://www.php.net/manual/en/solrquery.setexpandquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setExpandRows](https://www.php.net/manual/en/solrquery.setexpandrows.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setExplainOther](https://www.php.net/manual/en/solrquery.setexplainother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacet](https://www.php.net/manual/en/solrquery.setfacet.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetDateEnd](https://www.php.net/manual/en/solrquery.setfacetdateend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetDateGap](https://www.php.net/manual/en/solrquery.setfacetdategap.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetDateHardEnd](https://www.php.net/manual/en/solrquery.setfacetdatehardend.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetDateStart](https://www.php.net/manual/en/solrquery.setfacetdatestart.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetEnumCacheMinDefaultFrequency](https://www.php.net/manual/en/solrquery.setfacetenumcachemindefaultfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetLimit](https://www.php.net/manual/en/solrquery.setfacetlimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$limit`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetMethod](https://www.php.net/manual/en/solrquery.setfacetmethod.php)([string](https://www.php.net/manual/en/language.types.string.php) `$method`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetMinCount](https://www.php.net/manual/en/solrquery.setfacetmincount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$mincount`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetMissing](https://www.php.net/manual/en/solrquery.setfacetmissing.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetOffset](https://www.php.net/manual/en/solrquery.setfacetoffset.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetPrefix](https://www.php.net/manual/en/solrquery.setfacetprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$prefix`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setFacetSort](https://www.php.net/manual/en/solrquery.setfacetsort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$facetSort`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroup](https://www.php.net/manual/en/solrquery.setgroup.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupCachePercent](https://www.php.net/manual/en/solrquery.setgroupcachepercent.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$percent`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupFacet](https://www.php.net/manual/en/solrquery.setgroupfacet.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupFormat](https://www.php.net/manual/en/solrquery.setgroupformat.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupLimit](https://www.php.net/manual/en/solrquery.setgrouplimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupMain](https://www.php.net/manual/en/solrquery.setgroupmain.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupNGroups](https://www.php.net/manual/en/solrquery.setgroupngroups.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupOffset](https://www.php.net/manual/en/solrquery.setgroupoffset.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setGroupTruncate](https://www.php.net/manual/en/solrquery.setgrouptruncate.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlight](https://www.php.net/manual/en/solrquery.sethighlight.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightAlternateField](https://www.php.net/manual/en/solrquery.sethighlightalternatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightFormatter](https://www.php.net/manual/en/solrquery.sethighlightformatter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$formatter`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightFragmenter](https://www.php.net/manual/en/solrquery.sethighlightfragmenter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fragmenter`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightFragsize](https://www.php.net/manual/en/solrquery.sethighlightfragsize.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$size`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.sethighlighthighlightmultiterm.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.sethighlightmaxalternatefieldlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fieldLength`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightmaxanalyzedchars.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.sethighlightmergecontiguous.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightQuery](https://www.php.net/manual/en/solrquery.sethighlightquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightregexmaxanalyzedchars.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxAnalyzedChars`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightRegexPattern](https://www.php.net/manual/en/solrquery.sethighlightregexpattern.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightRegexSlop](https://www.php.net/manual/en/solrquery.sethighlightregexslop.php)([float](https://www.php.net/manual/en/language.types.float.php) `$factor`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.sethighlightrequirefieldmatch.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightSimplePost](https://www.php.net/manual/en/solrquery.sethighlightsimplepost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$simplePost`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightSimplePre](https://www.php.net/manual/en/solrquery.sethighlightsimplepre.php)([string](https://www.php.net/manual/en/language.types.string.php) `$simplePre`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightSnippets](https://www.php.net/manual/en/solrquery.sethighlightsnippets.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.sethighlightusephrasehighlighter.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMlt](https://www.php.net/manual/en/solrquery.setmlt.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltBoost](https://www.php.net/manual/en/solrquery.setmltboost.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltCount](https://www.php.net/manual/en/solrquery.setmltcount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$count`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.setmltmaxnumqueryterms.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMaxNumTokens](https://www.php.net/manual/en/solrquery.setmltmaxnumtokens.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMaxWordLength](https://www.php.net/manual/en/solrquery.setmltmaxwordlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxWordLength`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMinDocFrequency](https://www.php.net/manual/en/solrquery.setmltmindocfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minDocFrequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMinTermFrequency](https://www.php.net/manual/en/solrquery.setmltmintermfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minTermFrequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setMltMinWordLength](https://www.php.net/manual/en/solrquery.setmltminwordlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minWordLength`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setOmitHeader](https://www.php.net/manual/en/solrquery.setomitheader.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setQuery](https://www.php.net/manual/en/solrquery.setquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setRows](https://www.php.net/manual/en/solrquery.setrows.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$rows`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setShowDebugInfo](https://www.php.net/manual/en/solrquery.setshowdebuginfo.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setStart](https://www.php.net/manual/en/solrquery.setstart.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setStats](https://www.php.net/manual/en/solrquery.setstats.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTerms](https://www.php.net/manual/en/solrquery.setterms.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsField](https://www.php.net/manual/en/solrquery.settermsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldname`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.settermsincludelowerbound.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.settermsincludeupperbound.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsLimit](https://www.php.net/manual/en/solrquery.settermslimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$limit`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsLowerBound](https://www.php.net/manual/en/solrquery.settermslowerbound.php)([string](https://www.php.net/manual/en/language.types.string.php) `$lowerBound`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsMaxCount](https://www.php.net/manual/en/solrquery.settermsmaxcount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsMinCount](https://www.php.net/manual/en/solrquery.settermsmincount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsPrefix](https://www.php.net/manual/en/solrquery.settermsprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$prefix`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsReturnRaw](https://www.php.net/manual/en/solrquery.settermsreturnraw.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsSort](https://www.php.net/manual/en/solrquery.settermssort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$sortType`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTermsUpperBound](https://www.php.net/manual/en/solrquery.settermsupperbound.php)([string](https://www.php.net/manual/en/language.types.string.php) `$upperBound`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[setTimeAllowed](https://www.php.net/manual/en/solrquery.settimeallowed.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timeAllowed`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[\_\_destruct](https://www.php.net/manual/en/solrquery.destruct.php)()

/\\* Inherited methods \*/

public[SolrModifiableParams::\_\_construct](https://www.php.net/manual/en/solrmodifiableparams.construct.php)()

public[SolrModifiableParams::\_\_destruct](https://www.php.net/manual/en/solrmodifiableparams.destruct.php)()

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrquery.php\#solrquery.constants)

**`[SolrQuery::ORDER\_ASC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-asc)`**

Used to specify that the sorting should be in acending order

**`[SolrQuery::ORDER\_DESC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-desc)`**

Used to specify that the sorting should be in descending order

**`[SolrQuery::FACET\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-index)`**

Used to specify that the facet should sort by index

**`[SolrQuery::FACET\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-count)`**

Used to specify that the facet should sort by count

**`[SolrQuery::TERMS\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-index)`**

Used in the TermsComponent

**`[SolrQuery::TERMS\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-count)`**

Used in the TermsComponent

## Table of Contents [¶](https://www.php.net/manual/en/class.solrquery.php\#class.solrquery)

- [SolrQuery::addExpandFilterQuery](https://www.php.net/manual/en/solrquery.addexpandfilterquery.php) — Overrides main filter query, determines which documents to include in the main group
- [SolrQuery::addExpandSortField](https://www.php.net/manual/en/solrquery.addexpandsortfield.php) — Orders the documents within the expanded groups (expand.sort parameter)
- [SolrQuery::addFacetDateField](https://www.php.net/manual/en/solrquery.addfacetdatefield.php) — Maps to facet.date
- [SolrQuery::addFacetDateOther](https://www.php.net/manual/en/solrquery.addfacetdateother.php) — Adds another facet.date.other parameter
- [SolrQuery::addFacetField](https://www.php.net/manual/en/solrquery.addfacetfield.php) — Adds another field to the facet
- [SolrQuery::addFacetQuery](https://www.php.net/manual/en/solrquery.addfacetquery.php) — Adds a facet query
- [SolrQuery::addField](https://www.php.net/manual/en/solrquery.addfield.php) — Specifies which fields to return in the result
- [SolrQuery::addFilterQuery](https://www.php.net/manual/en/solrquery.addfilterquery.php) — Specifies a filter query
- [SolrQuery::addGroupField](https://www.php.net/manual/en/solrquery.addgroupfield.php) — Add a field to be used to group results
- [SolrQuery::addGroupFunction](https://www.php.net/manual/en/solrquery.addgroupfunction.php) — Allows grouping results based on the unique values of a function query (group.func parameter)
- [SolrQuery::addGroupQuery](https://www.php.net/manual/en/solrquery.addgroupquery.php) — Allows grouping of documents that match the given query
- [SolrQuery::addGroupSortField](https://www.php.net/manual/en/solrquery.addgroupsortfield.php) — Add a group sort field (group.sort parameter)
- [SolrQuery::addHighlightField](https://www.php.net/manual/en/solrquery.addhighlightfield.php) — Maps to hl.fl
- [SolrQuery::addMltField](https://www.php.net/manual/en/solrquery.addmltfield.php) — Sets a field to use for similarity
- [SolrQuery::addMltQueryField](https://www.php.net/manual/en/solrquery.addmltqueryfield.php) — Maps to mlt.qf
- [SolrQuery::addSortField](https://www.php.net/manual/en/solrquery.addsortfield.php) — Used to control how the results should be sorted
- [SolrQuery::addStatsFacet](https://www.php.net/manual/en/solrquery.addstatsfacet.php) — Requests a return of sub results for values within the given facet
- [SolrQuery::addStatsField](https://www.php.net/manual/en/solrquery.addstatsfield.php) — Maps to stats.field parameter
- [SolrQuery::collapse](https://www.php.net/manual/en/solrquery.collapse.php) — Collapses the result set to a single document per group
- [SolrQuery::\_\_construct](https://www.php.net/manual/en/solrquery.construct.php) — Constructor
- [SolrQuery::\_\_destruct](https://www.php.net/manual/en/solrquery.destruct.php) — Destructor
- [SolrQuery::getExpand](https://www.php.net/manual/en/solrquery.getexpand.php) — Returns true if group expanding is enabled
- [SolrQuery::getExpandFilterQueries](https://www.php.net/manual/en/solrquery.getexpandfilterqueries.php) — Returns the expand filter queries
- [SolrQuery::getExpandQuery](https://www.php.net/manual/en/solrquery.getexpandquery.php) — Returns the expand query expand.q parameter
- [SolrQuery::getExpandRows](https://www.php.net/manual/en/solrquery.getexpandrows.php) — Returns The number of rows to display in each group (expand.rows)
- [SolrQuery::getExpandSortFields](https://www.php.net/manual/en/solrquery.getexpandsortfields.php) — Returns an array of fields
- [SolrQuery::getFacet](https://www.php.net/manual/en/solrquery.getfacet.php) — Returns the value of the facet parameter
- [SolrQuery::getFacetDateEnd](https://www.php.net/manual/en/solrquery.getfacetdateend.php) — Returns the value for the facet.date.end parameter
- [SolrQuery::getFacetDateFields](https://www.php.net/manual/en/solrquery.getfacetdatefields.php) — Returns all the facet.date fields
- [SolrQuery::getFacetDateGap](https://www.php.net/manual/en/solrquery.getfacetdategap.php) — Returns the value of the facet.date.gap parameter
- [SolrQuery::getFacetDateHardEnd](https://www.php.net/manual/en/solrquery.getfacetdatehardend.php) — Returns the value of the facet.date.hardend parameter
- [SolrQuery::getFacetDateOther](https://www.php.net/manual/en/solrquery.getfacetdateother.php) — Returns the value for the facet.date.other parameter
- [SolrQuery::getFacetDateStart](https://www.php.net/manual/en/solrquery.getfacetdatestart.php) — Returns the lower bound for the first date range for all date faceting on this field
- [SolrQuery::getFacetFields](https://www.php.net/manual/en/solrquery.getfacetfields.php) — Returns all the facet fields
- [SolrQuery::getFacetLimit](https://www.php.net/manual/en/solrquery.getfacetlimit.php) — Returns the maximum number of constraint counts that should be returned for the facet fields
- [SolrQuery::getFacetMethod](https://www.php.net/manual/en/solrquery.getfacetmethod.php) — Returns the value of the facet.method parameter
- [SolrQuery::getFacetMinCount](https://www.php.net/manual/en/solrquery.getfacetmincount.php) — Returns the minimum counts for facet fields should be included in the response
- [SolrQuery::getFacetMissing](https://www.php.net/manual/en/solrquery.getfacetmissing.php) — Returns the current state of the facet.missing parameter
- [SolrQuery::getFacetOffset](https://www.php.net/manual/en/solrquery.getfacetoffset.php) — Returns an offset into the list of constraints to be used for pagination
- [SolrQuery::getFacetPrefix](https://www.php.net/manual/en/solrquery.getfacetprefix.php) — Returns the facet prefix
- [SolrQuery::getFacetQueries](https://www.php.net/manual/en/solrquery.getfacetqueries.php) — Returns all the facet queries
- [SolrQuery::getFacetSort](https://www.php.net/manual/en/solrquery.getfacetsort.php) — Returns the facet sort type
- [SolrQuery::getFields](https://www.php.net/manual/en/solrquery.getfields.php) — Returns the list of fields that will be returned in the response
- [SolrQuery::getFilterQueries](https://www.php.net/manual/en/solrquery.getfilterqueries.php) — Returns an array of filter queries
- [SolrQuery::getGroup](https://www.php.net/manual/en/solrquery.getgroup.php) — Returns true if grouping is enabled
- [SolrQuery::getGroupCachePercent](https://www.php.net/manual/en/solrquery.getgroupcachepercent.php) — Returns group cache percent value
- [SolrQuery::getGroupFacet](https://www.php.net/manual/en/solrquery.getgroupfacet.php) — Returns the group.facet parameter value
- [SolrQuery::getGroupFields](https://www.php.net/manual/en/solrquery.getgroupfields.php) — Returns group fields (group.field parameter values)
- [SolrQuery::getGroupFormat](https://www.php.net/manual/en/solrquery.getgroupformat.php) — Returns the group.format value
- [SolrQuery::getGroupFunctions](https://www.php.net/manual/en/solrquery.getgroupfunctions.php) — Returns group functions (group.func parameter values)
- [SolrQuery::getGroupLimit](https://www.php.net/manual/en/solrquery.getgrouplimit.php) — Returns the group.limit value
- [SolrQuery::getGroupMain](https://www.php.net/manual/en/solrquery.getgroupmain.php) — Returns the group.main value
- [SolrQuery::getGroupNGroups](https://www.php.net/manual/en/solrquery.getgroupngroups.php) — Returns the group.ngroups value
- [SolrQuery::getGroupOffset](https://www.php.net/manual/en/solrquery.getgroupoffset.php) — Returns the group.offset value
- [SolrQuery::getGroupQueries](https://www.php.net/manual/en/solrquery.getgroupqueries.php) — Returns all the group.query parameter values
- [SolrQuery::getGroupSortFields](https://www.php.net/manual/en/solrquery.getgroupsortfields.php) — Returns the group.sort value
- [SolrQuery::getGroupTruncate](https://www.php.net/manual/en/solrquery.getgrouptruncate.php) — Returns the group.truncate value
- [SolrQuery::getHighlight](https://www.php.net/manual/en/solrquery.gethighlight.php) — Returns the state of the hl parameter
- [SolrQuery::getHighlightAlternateField](https://www.php.net/manual/en/solrquery.gethighlightalternatefield.php) — Returns the highlight field to use as backup or default
- [SolrQuery::getHighlightFields](https://www.php.net/manual/en/solrquery.gethighlightfields.php) — Returns all the fields that Solr should generate highlighted snippets for
- [SolrQuery::getHighlightFormatter](https://www.php.net/manual/en/solrquery.gethighlightformatter.php) — Returns the formatter for the highlighted output
- [SolrQuery::getHighlightFragmenter](https://www.php.net/manual/en/solrquery.gethighlightfragmenter.php) — Returns the text snippet generator for highlighted text
- [SolrQuery::getHighlightFragsize](https://www.php.net/manual/en/solrquery.gethighlightfragsize.php) — Returns the number of characters of fragments to consider for highlighting
- [SolrQuery::getHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.gethighlighthighlightmultiterm.php) — Returns whether or not to enable highlighting for range/wildcard/fuzzy/prefix queries
- [SolrQuery::getHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.gethighlightmaxalternatefieldlength.php) — Returns the maximum number of characters of the field to return
- [SolrQuery::getHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightmaxanalyzedchars.php) — Returns the maximum number of characters into a document to look for suitable snippets
- [SolrQuery::getHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.gethighlightmergecontiguous.php) — Returns whether or not the collapse contiguous fragments into a single fragment
- [SolrQuery::getHighlightQuery](https://www.php.net/manual/en/solrquery.gethighlightquery.php) — return the highlightquery (hl.q)
- [SolrQuery::getHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightregexmaxanalyzedchars.php) — Returns the maximum number of characters from a field when using the regex fragmenter
- [SolrQuery::getHighlightRegexPattern](https://www.php.net/manual/en/solrquery.gethighlightregexpattern.php) — Returns the regular expression for fragmenting
- [SolrQuery::getHighlightRegexSlop](https://www.php.net/manual/en/solrquery.gethighlightregexslop.php) — Returns the deviation factor from the ideal fragment size
- [SolrQuery::getHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.gethighlightrequirefieldmatch.php) — Returns if a field will only be highlighted if the query matched in this particular field
- [SolrQuery::getHighlightSimplePost](https://www.php.net/manual/en/solrquery.gethighlightsimplepost.php) — Returns the text which appears after a highlighted term
- [SolrQuery::getHighlightSimplePre](https://www.php.net/manual/en/solrquery.gethighlightsimplepre.php) — Returns the text which appears before a highlighted term
- [SolrQuery::getHighlightSnippets](https://www.php.net/manual/en/solrquery.gethighlightsnippets.php) — Returns the maximum number of highlighted snippets to generate per field
- [SolrQuery::getHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.gethighlightusephrasehighlighter.php) — Returns the state of the hl.usePhraseHighlighter parameter
- [SolrQuery::getMlt](https://www.php.net/manual/en/solrquery.getmlt.php) — Returns whether or not MoreLikeThis results should be enabled
- [SolrQuery::getMltBoost](https://www.php.net/manual/en/solrquery.getmltboost.php) — Returns whether or not the query will be boosted by the interesting term relevance
- [SolrQuery::getMltCount](https://www.php.net/manual/en/solrquery.getmltcount.php) — Returns the number of similar documents to return for each result
- [SolrQuery::getMltFields](https://www.php.net/manual/en/solrquery.getmltfields.php) — Returns all the fields to use for similarity
- [SolrQuery::getMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.getmltmaxnumqueryterms.php) — Returns the maximum number of query terms that will be included in any generated query
- [SolrQuery::getMltMaxNumTokens](https://www.php.net/manual/en/solrquery.getmltmaxnumtokens.php) — Returns the maximum number of tokens to parse in each document field that is not stored with TermVector support
- [SolrQuery::getMltMaxWordLength](https://www.php.net/manual/en/solrquery.getmltmaxwordlength.php) — Returns the maximum word length above which words will be ignored
- [SolrQuery::getMltMinDocFrequency](https://www.php.net/manual/en/solrquery.getmltmindocfrequency.php) — Returns the treshold frequency at which words will be ignored which do not occur in at least this many docs
- [SolrQuery::getMltMinTermFrequency](https://www.php.net/manual/en/solrquery.getmltmintermfrequency.php) — Returns the frequency below which terms will be ignored in the source document
- [SolrQuery::getMltMinWordLength](https://www.php.net/manual/en/solrquery.getmltminwordlength.php) — Returns the minimum word length below which words will be ignored
- [SolrQuery::getMltQueryFields](https://www.php.net/manual/en/solrquery.getmltqueryfields.php) — Returns the query fields and their boosts
- [SolrQuery::getQuery](https://www.php.net/manual/en/solrquery.getquery.php) — Returns the main query
- [SolrQuery::getRows](https://www.php.net/manual/en/solrquery.getrows.php) — Returns the maximum number of documents
- [SolrQuery::getSortFields](https://www.php.net/manual/en/solrquery.getsortfields.php) — Returns all the sort fields
- [SolrQuery::getStart](https://www.php.net/manual/en/solrquery.getstart.php) — Returns the offset in the complete result set
- [SolrQuery::getStats](https://www.php.net/manual/en/solrquery.getstats.php) — Returns whether or not stats is enabled
- [SolrQuery::getStatsFacets](https://www.php.net/manual/en/solrquery.getstatsfacets.php) — Returns all the stats facets that were set
- [SolrQuery::getStatsFields](https://www.php.net/manual/en/solrquery.getstatsfields.php) — Returns all the statistics fields
- [SolrQuery::getTerms](https://www.php.net/manual/en/solrquery.getterms.php) — Returns whether or not the TermsComponent is enabled
- [SolrQuery::getTermsField](https://www.php.net/manual/en/solrquery.gettermsfield.php) — Returns the field from which the terms are retrieved
- [SolrQuery::getTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.gettermsincludelowerbound.php) — Returns whether or not to include the lower bound in the result set
- [SolrQuery::getTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.gettermsincludeupperbound.php) — Returns whether or not to include the upper bound term in the result set
- [SolrQuery::getTermsLimit](https://www.php.net/manual/en/solrquery.gettermslimit.php) — Returns the maximum number of terms Solr should return
- [SolrQuery::getTermsLowerBound](https://www.php.net/manual/en/solrquery.gettermslowerbound.php) — Returns the term to start at
- [SolrQuery::getTermsMaxCount](https://www.php.net/manual/en/solrquery.gettermsmaxcount.php) — Returns the maximum document frequency
- [SolrQuery::getTermsMinCount](https://www.php.net/manual/en/solrquery.gettermsmincount.php) — Returns the minimum document frequency to return in order to be included
- [SolrQuery::getTermsPrefix](https://www.php.net/manual/en/solrquery.gettermsprefix.php) — Returns the term prefix
- [SolrQuery::getTermsReturnRaw](https://www.php.net/manual/en/solrquery.gettermsreturnraw.php) — Whether or not to return raw characters
- [SolrQuery::getTermsSort](https://www.php.net/manual/en/solrquery.gettermssort.php) — Returns an integer indicating how terms are sorted
- [SolrQuery::getTermsUpperBound](https://www.php.net/manual/en/solrquery.gettermsupperbound.php) — Returns the term to stop at
- [SolrQuery::getTimeAllowed](https://www.php.net/manual/en/solrquery.gettimeallowed.php) — Returns the time in milliseconds allowed for the query to finish
- [SolrQuery::removeExpandFilterQuery](https://www.php.net/manual/en/solrquery.removeexpandfilterquery.php) — Removes an expand filter query
- [SolrQuery::removeExpandSortField](https://www.php.net/manual/en/solrquery.removeexpandsortfield.php) — Removes an expand sort field from the expand.sort parameter
- [SolrQuery::removeFacetDateField](https://www.php.net/manual/en/solrquery.removefacetdatefield.php) — Removes one of the facet date fields
- [SolrQuery::removeFacetDateOther](https://www.php.net/manual/en/solrquery.removefacetdateother.php) — Removes one of the facet.date.other parameters
- [SolrQuery::removeFacetField](https://www.php.net/manual/en/solrquery.removefacetfield.php) — Removes one of the facet.date parameters
- [SolrQuery::removeFacetQuery](https://www.php.net/manual/en/solrquery.removefacetquery.php) — Removes one of the facet.query parameters
- [SolrQuery::removeField](https://www.php.net/manual/en/solrquery.removefield.php) — Removes a field from the list of fields
- [SolrQuery::removeFilterQuery](https://www.php.net/manual/en/solrquery.removefilterquery.php) — Removes a filter query
- [SolrQuery::removeHighlightField](https://www.php.net/manual/en/solrquery.removehighlightfield.php) — Removes one of the fields used for highlighting
- [SolrQuery::removeMltField](https://www.php.net/manual/en/solrquery.removemltfield.php) — Removes one of the moreLikeThis fields
- [SolrQuery::removeMltQueryField](https://www.php.net/manual/en/solrquery.removemltqueryfield.php) — Removes one of the moreLikeThis query fields
- [SolrQuery::removeSortField](https://www.php.net/manual/en/solrquery.removesortfield.php) — Removes one of the sort fields
- [SolrQuery::removeStatsFacet](https://www.php.net/manual/en/solrquery.removestatsfacet.php) — Removes one of the stats.facet parameters
- [SolrQuery::removeStatsField](https://www.php.net/manual/en/solrquery.removestatsfield.php) — Removes one of the stats.field parameters
- [SolrQuery::setEchoHandler](https://www.php.net/manual/en/solrquery.setechohandler.php) — Toggles the echoHandler parameter
- [SolrQuery::setEchoParams](https://www.php.net/manual/en/solrquery.setechoparams.php) — Determines what kind of parameters to include in the response
- [SolrQuery::setExpand](https://www.php.net/manual/en/solrquery.setexpand.php) — Enables/Disables the Expand Component
- [SolrQuery::setExpandQuery](https://www.php.net/manual/en/solrquery.setexpandquery.php) — Sets the expand.q parameter
- [SolrQuery::setExpandRows](https://www.php.net/manual/en/solrquery.setexpandrows.php) — Sets the number of rows to display in each group (expand.rows). Server Default 5
- [SolrQuery::setExplainOther](https://www.php.net/manual/en/solrquery.setexplainother.php) — Sets the explainOther common query parameter
- [SolrQuery::setFacet](https://www.php.net/manual/en/solrquery.setfacet.php) — Maps to the facet parameter. Enables or disables facetting
- [SolrQuery::setFacetDateEnd](https://www.php.net/manual/en/solrquery.setfacetdateend.php) — Maps to facet.date.end
- [SolrQuery::setFacetDateGap](https://www.php.net/manual/en/solrquery.setfacetdategap.php) — Maps to facet.date.gap
- [SolrQuery::setFacetDateHardEnd](https://www.php.net/manual/en/solrquery.setfacetdatehardend.php) — Maps to facet.date.hardend
- [SolrQuery::setFacetDateStart](https://www.php.net/manual/en/solrquery.setfacetdatestart.php) — Maps to facet.date.start
- [SolrQuery::setFacetEnumCacheMinDefaultFrequency](https://www.php.net/manual/en/solrquery.setfacetenumcachemindefaultfrequency.php) — Sets the minimum document frequency used for determining term count
- [SolrQuery::setFacetLimit](https://www.php.net/manual/en/solrquery.setfacetlimit.php) — Maps to facet.limit
- [SolrQuery::setFacetMethod](https://www.php.net/manual/en/solrquery.setfacetmethod.php) — Specifies the type of algorithm to use when faceting a field
- [SolrQuery::setFacetMinCount](https://www.php.net/manual/en/solrquery.setfacetmincount.php) — Maps to facet.mincount
- [SolrQuery::setFacetMissing](https://www.php.net/manual/en/solrquery.setfacetmissing.php) — Maps to facet.missing
- [SolrQuery::setFacetOffset](https://www.php.net/manual/en/solrquery.setfacetoffset.php) — Sets the offset into the list of constraints to allow for pagination
- [SolrQuery::setFacetPrefix](https://www.php.net/manual/en/solrquery.setfacetprefix.php) — Specifies a string prefix with which to limits the terms on which to facet
- [SolrQuery::setFacetSort](https://www.php.net/manual/en/solrquery.setfacetsort.php) — Determines the ordering of the facet field constraints
- [SolrQuery::setGroup](https://www.php.net/manual/en/solrquery.setgroup.php) — Enable/Disable result grouping (group parameter)
- [SolrQuery::setGroupCachePercent](https://www.php.net/manual/en/solrquery.setgroupcachepercent.php) — Enables caching for result grouping
- [SolrQuery::setGroupFacet](https://www.php.net/manual/en/solrquery.setgroupfacet.php) — Sets group.facet parameter
- [SolrQuery::setGroupFormat](https://www.php.net/manual/en/solrquery.setgroupformat.php) — Sets the group format, result structure (group.format parameter)
- [SolrQuery::setGroupLimit](https://www.php.net/manual/en/solrquery.setgrouplimit.php) — Specifies the number of results to return for each group. The server default value is 1
- [SolrQuery::setGroupMain](https://www.php.net/manual/en/solrquery.setgroupmain.php) — If true, the result of the first field grouping command is used as the main result list in the response, using group.format=simple
- [SolrQuery::setGroupNGroups](https://www.php.net/manual/en/solrquery.setgroupngroups.php) — If true, Solr includes the number of groups that have matched the query in the results
- [SolrQuery::setGroupOffset](https://www.php.net/manual/en/solrquery.setgroupoffset.php) — Sets the group.offset parameter
- [SolrQuery::setGroupTruncate](https://www.php.net/manual/en/solrquery.setgrouptruncate.php) — If true, facet counts are based on the most relevant document of each group matching the query
- [SolrQuery::setHighlight](https://www.php.net/manual/en/solrquery.sethighlight.php) — Enables or disables highlighting
- [SolrQuery::setHighlightAlternateField](https://www.php.net/manual/en/solrquery.sethighlightalternatefield.php) — Specifies the backup field to use
- [SolrQuery::setHighlightFormatter](https://www.php.net/manual/en/solrquery.sethighlightformatter.php) — Specify a formatter for the highlight output
- [SolrQuery::setHighlightFragmenter](https://www.php.net/manual/en/solrquery.sethighlightfragmenter.php) — Sets a text snippet generator for highlighted text
- [SolrQuery::setHighlightFragsize](https://www.php.net/manual/en/solrquery.sethighlightfragsize.php) — The size of fragments to consider for highlighting
- [SolrQuery::setHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.sethighlighthighlightmultiterm.php) — Use SpanScorer to highlight phrase terms
- [SolrQuery::setHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.sethighlightmaxalternatefieldlength.php) — Sets the maximum number of characters of the field to return
- [SolrQuery::setHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightmaxanalyzedchars.php) — Specifies the number of characters into a document to look for suitable snippets
- [SolrQuery::setHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.sethighlightmergecontiguous.php) — Whether or not to collapse contiguous fragments into a single fragment
- [SolrQuery::setHighlightQuery](https://www.php.net/manual/en/solrquery.sethighlightquery.php) — A query designated for highlighting (hl.q)
- [SolrQuery::setHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightregexmaxanalyzedchars.php) — Specify the maximum number of characters to analyze
- [SolrQuery::setHighlightRegexPattern](https://www.php.net/manual/en/solrquery.sethighlightregexpattern.php) — Specify the regular expression for fragmenting
- [SolrQuery::setHighlightRegexSlop](https://www.php.net/manual/en/solrquery.sethighlightregexslop.php) — Sets the factor by which the regex fragmenter can stray from the ideal fragment size
- [SolrQuery::setHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.sethighlightrequirefieldmatch.php) — Require field matching during highlighting
- [SolrQuery::setHighlightSimplePost](https://www.php.net/manual/en/solrquery.sethighlightsimplepost.php) — Sets the text which appears after a highlighted term
- [SolrQuery::setHighlightSimplePre](https://www.php.net/manual/en/solrquery.sethighlightsimplepre.php) — Sets the text which appears before a highlighted term
- [SolrQuery::setHighlightSnippets](https://www.php.net/manual/en/solrquery.sethighlightsnippets.php) — Sets the maximum number of highlighted snippets to generate per field
- [SolrQuery::setHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.sethighlightusephrasehighlighter.php) — Whether to highlight phrase terms only when they appear within the query phrase
- [SolrQuery::setMlt](https://www.php.net/manual/en/solrquery.setmlt.php) — Enables or disables moreLikeThis
- [SolrQuery::setMltBoost](https://www.php.net/manual/en/solrquery.setmltboost.php) — Set if the query will be boosted by the interesting term relevance
- [SolrQuery::setMltCount](https://www.php.net/manual/en/solrquery.setmltcount.php) — Set the number of similar documents to return for each result
- [SolrQuery::setMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.setmltmaxnumqueryterms.php) — Sets the maximum number of query terms included
- [SolrQuery::setMltMaxNumTokens](https://www.php.net/manual/en/solrquery.setmltmaxnumtokens.php) — Specifies the maximum number of tokens to parse
- [SolrQuery::setMltMaxWordLength](https://www.php.net/manual/en/solrquery.setmltmaxwordlength.php) — Sets the maximum word length
- [SolrQuery::setMltMinDocFrequency](https://www.php.net/manual/en/solrquery.setmltmindocfrequency.php) — Sets the mltMinDoc frequency
- [SolrQuery::setMltMinTermFrequency](https://www.php.net/manual/en/solrquery.setmltmintermfrequency.php) — Sets the frequency below which terms will be ignored in the source docs
- [SolrQuery::setMltMinWordLength](https://www.php.net/manual/en/solrquery.setmltminwordlength.php) — Sets the minimum word length
- [SolrQuery::setOmitHeader](https://www.php.net/manual/en/solrquery.setomitheader.php) — Exclude the header from the returned results
- [SolrQuery::setQuery](https://www.php.net/manual/en/solrquery.setquery.php) — Sets the search query
- [SolrQuery::setRows](https://www.php.net/manual/en/solrquery.setrows.php) — Specifies the maximum number of rows to return in the result
- [SolrQuery::setShowDebugInfo](https://www.php.net/manual/en/solrquery.setshowdebuginfo.php) — Flag to show debug information
- [SolrQuery::setStart](https://www.php.net/manual/en/solrquery.setstart.php) — Specifies the number of rows to skip
- [SolrQuery::setStats](https://www.php.net/manual/en/solrquery.setstats.php) — Enables or disables the Stats component
- [SolrQuery::setTerms](https://www.php.net/manual/en/solrquery.setterms.php) — Enables or disables the TermsComponent
- [SolrQuery::setTermsField](https://www.php.net/manual/en/solrquery.settermsfield.php) — Sets the name of the field to get the Terms from
- [SolrQuery::setTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.settermsincludelowerbound.php) — Include the lower bound term in the result set
- [SolrQuery::setTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.settermsincludeupperbound.php) — Include the upper bound term in the result set
- [SolrQuery::setTermsLimit](https://www.php.net/manual/en/solrquery.settermslimit.php) — Sets the maximum number of terms to return
- [SolrQuery::setTermsLowerBound](https://www.php.net/manual/en/solrquery.settermslowerbound.php) — Specifies the Term to start from
- [SolrQuery::setTermsMaxCount](https://www.php.net/manual/en/solrquery.settermsmaxcount.php) — Sets the maximum document frequency
- [SolrQuery::setTermsMinCount](https://www.php.net/manual/en/solrquery.settermsmincount.php) — Sets the minimum document frequency
- [SolrQuery::setTermsPrefix](https://www.php.net/manual/en/solrquery.settermsprefix.php) — Restrict matches to terms that start with the prefix
- [SolrQuery::setTermsReturnRaw](https://www.php.net/manual/en/solrquery.settermsreturnraw.php) — Return the raw characters of the indexed term
- [SolrQuery::setTermsSort](https://www.php.net/manual/en/solrquery.settermssort.php) — Specifies how to sort the returned terms
- [SolrQuery::setTermsUpperBound](https://www.php.net/manual/en/solrquery.settermsupperbound.php) — Sets the term to stop at
- [SolrQuery::setTimeAllowed](https://www.php.net/manual/en/solrquery.settimeallowed.php) — The time allowed for search to finish

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrquery.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrquery%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrquery&repo=en&redirect=https://www.php.net/manual/en/class.solrquery.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=107308&page=class.solrquery&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107308&page=class.solrquery&vote=down "Vote down!")

5


[**_andy at borkedcoder dot com_**](https://www.php.net/manual/en/class.solrquery.php#107308) [¶](https://www.php.net/manual/en/class.solrquery.php#107308)

**13 years ago**

`Note - if using morelikethis, and your query is on a numeric ID, then you will not be able to access the moreLikeThis object in the results...
when q=id:3493 searching with mlt, result is:
SolrObject Object
(
...
    [moreLikeThis] => SolrObject Object
        (
            [3493] => SolrObject Object
                (
                    [numFound] => 6286
                    [start] => 0
                    [docs] => Array
                        (
....etc
the numeric object name (3493 above) is impossible to access
not by $response->moreLikeThis->{3493} nor $response->moreLikeThis->{'3493'}, nothing...
only way is to convert the moreLikeThis object into an array with:
$response_array = (array) $response->moreLikeThis;
then iterate the array as the array key is known.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrquery&repo=en&redirect=https://www.php.net/manual/en/class.solrquery.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google