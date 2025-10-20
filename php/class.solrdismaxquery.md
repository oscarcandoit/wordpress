---
url: https://www.php.net/manual/en/class.solrdismaxquery.php
scraped_at: 2025-10-20T02:38:38.655Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrDisMaxQuery class [¶](https://www.php.net/manual/en/class.solrdismaxquery.php\#class.solrdismaxquery)

(No version information available, might only be in Git)

## Introduction [¶](https://www.php.net/manual/en/class.solrdismaxquery.php\#solrdismaxquery.intro)

## Class synopsis [¶](https://www.php.net/manual/en/class.solrdismaxquery.php\#solrdismaxquery.synopsis)

class **SolrDisMaxQuery**extends [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)implements [Serializable](https://www.php.net/manual/en/class.serializable.php) {

/\\* Inherited properties \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::ORDER\_ASC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-asc) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::ORDER\_DESC](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.order-desc) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::FACET\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-index) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::FACET\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.facet-sort-count) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::TERMS\_SORT\_INDEX](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-index) = 0;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SolrQuery::TERMS\_SORT\_COUNT](https://www.php.net/manual/en/class.solrquery.php#solrquery.constants.terms-sort-count) = 1;

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrdismaxquery.construct.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q` = ?)

public[addBigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.addbigramphrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$boost`, [string](https://www.php.net/manual/en/language.types.string.php) `$slop` = ?): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[addBoostQuery](https://www.php.net/manual/en/solrdismaxquery.addboostquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$boost` = ?): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[addPhraseField](https://www.php.net/manual/en/solrdismaxquery.addphrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$boost`, [string](https://www.php.net/manual/en/language.types.string.php) `$slop` = ?): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[addQueryField](https://www.php.net/manual/en/solrdismaxquery.addqueryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$boost` = ?): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[addTrigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.addtrigramphrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$boost`, [string](https://www.php.net/manual/en/language.types.string.php) `$slop` = ?): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[addUserField](https://www.php.net/manual/en/solrdismaxquery.adduserfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removeBigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.removebigramphrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removeBoostQuery](https://www.php.net/manual/en/solrdismaxquery.removeboostquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removePhraseField](https://www.php.net/manual/en/solrdismaxquery.removephrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removeQueryField](https://www.php.net/manual/en/solrdismaxquery.removequeryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removeTrigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.removetrigramphrasefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[removeUserField](https://www.php.net/manual/en/solrdismaxquery.removeuserfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setBigramPhraseFields](https://www.php.net/manual/en/solrdismaxquery.setbigramphrasefields.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fields`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setBigramPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setbigramphraseslop.php)([string](https://www.php.net/manual/en/language.types.string.php) `$slop`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setBoostFunction](https://www.php.net/manual/en/solrdismaxquery.setboostfunction.php)([string](https://www.php.net/manual/en/language.types.string.php) `$function`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setBoostQuery](https://www.php.net/manual/en/solrdismaxquery.setboostquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setMinimumMatch](https://www.php.net/manual/en/solrdismaxquery.setminimummatch.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setPhraseFields](https://www.php.net/manual/en/solrdismaxquery.setphrasefields.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fields`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setphraseslop.php)([string](https://www.php.net/manual/en/language.types.string.php) `$slop`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setQueryAlt](https://www.php.net/manual/en/solrdismaxquery.setqueryalt.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setQueryPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setqueryphraseslop.php)([string](https://www.php.net/manual/en/language.types.string.php) `$slop`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setTieBreaker](https://www.php.net/manual/en/solrdismaxquery.settiebreaker.php)([string](https://www.php.net/manual/en/language.types.string.php) `$tieBreaker`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setTrigramPhraseFields](https://www.php.net/manual/en/solrdismaxquery.settrigramphrasefields.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fields`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setTrigramPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.settrigramphraseslop.php)([string](https://www.php.net/manual/en/language.types.string.php) `$slop`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[setUserFields](https://www.php.net/manual/en/solrdismaxquery.setuserfields.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fields`): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[useDisMaxQueryParser](https://www.php.net/manual/en/solrdismaxquery.usedismaxqueryparser.php)(): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

public[useEDisMaxQueryParser](https://www.php.net/manual/en/solrdismaxquery.useedismaxqueryparser.php)(): [SolrDisMaxQuery](https://www.php.net/manual/en/class.solrdismaxquery.php)

/\\* Inherited methods \*/

public[SolrQuery::addExpandFilterQuery](https://www.php.net/manual/en/solrquery.addexpandfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addExpandSortField](https://www.php.net/manual/en/solrquery.addexpandsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$order` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addFacetDateField](https://www.php.net/manual/en/solrquery.addfacetdatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$dateField`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addFacetDateOther](https://www.php.net/manual/en/solrquery.addfacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addFacetField](https://www.php.net/manual/en/solrquery.addfacetfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addFacetQuery](https://www.php.net/manual/en/solrquery.addfacetquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$facetQuery`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addField](https://www.php.net/manual/en/solrquery.addfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addFilterQuery](https://www.php.net/manual/en/solrquery.addfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addGroupField](https://www.php.net/manual/en/solrquery.addgroupfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addGroupFunction](https://www.php.net/manual/en/solrquery.addgroupfunction.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addGroupQuery](https://www.php.net/manual/en/solrquery.addgroupquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addGroupSortField](https://www.php.net/manual/en/solrquery.addgroupsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [int](https://www.php.net/manual/en/language.types.integer.php) `$order` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addHighlightField](https://www.php.net/manual/en/solrquery.addhighlightfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addMltField](https://www.php.net/manual/en/solrquery.addmltfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addMltQueryField](https://www.php.net/manual/en/solrquery.addmltqueryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [float](https://www.php.net/manual/en/language.types.float.php) `$boost`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addSortField](https://www.php.net/manual/en/solrquery.addsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [int](https://www.php.net/manual/en/language.types.integer.php) `$order` = SolrQuery::ORDER\_DESC): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addStatsFacet](https://www.php.net/manual/en/solrquery.addstatsfacet.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::addStatsField](https://www.php.net/manual/en/solrquery.addstatsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::collapse](https://www.php.net/manual/en/solrquery.collapse.php)([SolrCollapseFunction](https://www.php.net/manual/en/class.solrcollapsefunction.php) `$collapseFunction`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::getExpand](https://www.php.net/manual/en/solrquery.getexpand.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getExpandFilterQueries](https://www.php.net/manual/en/solrquery.getexpandfilterqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getExpandQuery](https://www.php.net/manual/en/solrquery.getexpandquery.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getExpandRows](https://www.php.net/manual/en/solrquery.getexpandrows.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getExpandSortFields](https://www.php.net/manual/en/solrquery.getexpandsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFacet](https://www.php.net/manual/en/solrquery.getfacet.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getFacetDateEnd](https://www.php.net/manual/en/solrquery.getfacetdateend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetDateFields](https://www.php.net/manual/en/solrquery.getfacetdatefields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFacetDateGap](https://www.php.net/manual/en/solrquery.getfacetdategap.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetDateHardEnd](https://www.php.net/manual/en/solrquery.getfacetdatehardend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetDateOther](https://www.php.net/manual/en/solrquery.getfacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFacetDateStart](https://www.php.net/manual/en/solrquery.getfacetdatestart.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetFields](https://www.php.net/manual/en/solrquery.getfacetfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFacetLimit](https://www.php.net/manual/en/solrquery.getfacetlimit.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getFacetMethod](https://www.php.net/manual/en/solrquery.getfacetmethod.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetMinCount](https://www.php.net/manual/en/solrquery.getfacetmincount.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getFacetMissing](https://www.php.net/manual/en/solrquery.getfacetmissing.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getFacetOffset](https://www.php.net/manual/en/solrquery.getfacetoffset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getFacetPrefix](https://www.php.net/manual/en/solrquery.getfacetprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getFacetQueries](https://www.php.net/manual/en/solrquery.getfacetqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFacetSort](https://www.php.net/manual/en/solrquery.getfacetsort.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getFields](https://www.php.net/manual/en/solrquery.getfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getFilterQueries](https://www.php.net/manual/en/solrquery.getfilterqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getGroup](https://www.php.net/manual/en/solrquery.getgroup.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getGroupCachePercent](https://www.php.net/manual/en/solrquery.getgroupcachepercent.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getGroupFacet](https://www.php.net/manual/en/solrquery.getgroupfacet.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getGroupFields](https://www.php.net/manual/en/solrquery.getgroupfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getGroupFormat](https://www.php.net/manual/en/solrquery.getgroupformat.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getGroupFunctions](https://www.php.net/manual/en/solrquery.getgroupfunctions.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getGroupLimit](https://www.php.net/manual/en/solrquery.getgrouplimit.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getGroupMain](https://www.php.net/manual/en/solrquery.getgroupmain.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getGroupNGroups](https://www.php.net/manual/en/solrquery.getgroupngroups.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getGroupOffset](https://www.php.net/manual/en/solrquery.getgroupoffset.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getGroupQueries](https://www.php.net/manual/en/solrquery.getgroupqueries.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getGroupSortFields](https://www.php.net/manual/en/solrquery.getgroupsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getGroupTruncate](https://www.php.net/manual/en/solrquery.getgrouptruncate.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getHighlight](https://www.php.net/manual/en/solrquery.gethighlight.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getHighlightAlternateField](https://www.php.net/manual/en/solrquery.gethighlightalternatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightFields](https://www.php.net/manual/en/solrquery.gethighlightfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getHighlightFormatter](https://www.php.net/manual/en/solrquery.gethighlightformatter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightFragmenter](https://www.php.net/manual/en/solrquery.gethighlightfragmenter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightFragsize](https://www.php.net/manual/en/solrquery.gethighlightfragsize.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.gethighlighthighlightmultiterm.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.gethighlightmaxalternatefieldlength.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightmaxanalyzedchars.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.gethighlightmergecontiguous.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getHighlightQuery](https://www.php.net/manual/en/solrquery.gethighlightquery.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.gethighlightregexmaxanalyzedchars.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getHighlightRegexPattern](https://www.php.net/manual/en/solrquery.gethighlightregexpattern.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightRegexSlop](https://www.php.net/manual/en/solrquery.gethighlightregexslop.php)(): [float](https://www.php.net/manual/en/language.types.float.php)

public[SolrQuery::getHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.gethighlightrequirefieldmatch.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getHighlightSimplePost](https://www.php.net/manual/en/solrquery.gethighlightsimplepost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightSimplePre](https://www.php.net/manual/en/solrquery.gethighlightsimplepre.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getHighlightSnippets](https://www.php.net/manual/en/solrquery.gethighlightsnippets.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.gethighlightusephrasehighlighter.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getMlt](https://www.php.net/manual/en/solrquery.getmlt.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getMltBoost](https://www.php.net/manual/en/solrquery.getmltboost.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getMltCount](https://www.php.net/manual/en/solrquery.getmltcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltFields](https://www.php.net/manual/en/solrquery.getmltfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.getmltmaxnumqueryterms.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltMaxNumTokens](https://www.php.net/manual/en/solrquery.getmltmaxnumtokens.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltMaxWordLength](https://www.php.net/manual/en/solrquery.getmltmaxwordlength.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltMinDocFrequency](https://www.php.net/manual/en/solrquery.getmltmindocfrequency.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltMinTermFrequency](https://www.php.net/manual/en/solrquery.getmltmintermfrequency.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltMinWordLength](https://www.php.net/manual/en/solrquery.getmltminwordlength.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getMltQueryFields](https://www.php.net/manual/en/solrquery.getmltqueryfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getQuery](https://www.php.net/manual/en/solrquery.getquery.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getRows](https://www.php.net/manual/en/solrquery.getrows.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getSortFields](https://www.php.net/manual/en/solrquery.getsortfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getStart](https://www.php.net/manual/en/solrquery.getstart.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getStats](https://www.php.net/manual/en/solrquery.getstats.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getStatsFacets](https://www.php.net/manual/en/solrquery.getstatsfacets.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getStatsFields](https://www.php.net/manual/en/solrquery.getstatsfields.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[SolrQuery::getTerms](https://www.php.net/manual/en/solrquery.getterms.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getTermsField](https://www.php.net/manual/en/solrquery.gettermsfield.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.gettermsincludelowerbound.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.gettermsincludeupperbound.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getTermsLimit](https://www.php.net/manual/en/solrquery.gettermslimit.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getTermsLowerBound](https://www.php.net/manual/en/solrquery.gettermslowerbound.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getTermsMaxCount](https://www.php.net/manual/en/solrquery.gettermsmaxcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getTermsMinCount](https://www.php.net/manual/en/solrquery.gettermsmincount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getTermsPrefix](https://www.php.net/manual/en/solrquery.gettermsprefix.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getTermsReturnRaw](https://www.php.net/manual/en/solrquery.gettermsreturnraw.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[SolrQuery::getTermsSort](https://www.php.net/manual/en/solrquery.gettermssort.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::getTermsUpperBound](https://www.php.net/manual/en/solrquery.gettermsupperbound.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[SolrQuery::getTimeAllowed](https://www.php.net/manual/en/solrquery.gettimeallowed.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[SolrQuery::removeExpandFilterQuery](https://www.php.net/manual/en/solrquery.removeexpandfilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeExpandSortField](https://www.php.net/manual/en/solrquery.removeexpandsortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeFacetDateField](https://www.php.net/manual/en/solrquery.removefacetdatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeFacetDateOther](https://www.php.net/manual/en/solrquery.removefacetdateother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeFacetField](https://www.php.net/manual/en/solrquery.removefacetfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeFacetQuery](https://www.php.net/manual/en/solrquery.removefacetquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeField](https://www.php.net/manual/en/solrquery.removefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeFilterQuery](https://www.php.net/manual/en/solrquery.removefilterquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fq`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeHighlightField](https://www.php.net/manual/en/solrquery.removehighlightfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeMltField](https://www.php.net/manual/en/solrquery.removemltfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeMltQueryField](https://www.php.net/manual/en/solrquery.removemltqueryfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$queryField`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeSortField](https://www.php.net/manual/en/solrquery.removesortfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeStatsFacet](https://www.php.net/manual/en/solrquery.removestatsfacet.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::removeStatsField](https://www.php.net/manual/en/solrquery.removestatsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setEchoHandler](https://www.php.net/manual/en/solrquery.setechohandler.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setEchoParams](https://www.php.net/manual/en/solrquery.setechoparams.php)([string](https://www.php.net/manual/en/language.types.string.php) `$type`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setExpand](https://www.php.net/manual/en/solrquery.setexpand.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setExpandQuery](https://www.php.net/manual/en/solrquery.setexpandquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setExpandRows](https://www.php.net/manual/en/solrquery.setexpandrows.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setExplainOther](https://www.php.net/manual/en/solrquery.setexplainother.php)([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacet](https://www.php.net/manual/en/solrquery.setfacet.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetDateEnd](https://www.php.net/manual/en/solrquery.setfacetdateend.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetDateGap](https://www.php.net/manual/en/solrquery.setfacetdategap.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetDateHardEnd](https://www.php.net/manual/en/solrquery.setfacetdatehardend.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetDateStart](https://www.php.net/manual/en/solrquery.setfacetdatestart.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetEnumCacheMinDefaultFrequency](https://www.php.net/manual/en/solrquery.setfacetenumcachemindefaultfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetLimit](https://www.php.net/manual/en/solrquery.setfacetlimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$limit`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetMethod](https://www.php.net/manual/en/solrquery.setfacetmethod.php)([string](https://www.php.net/manual/en/language.types.string.php) `$method`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetMinCount](https://www.php.net/manual/en/solrquery.setfacetmincount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$mincount`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetMissing](https://www.php.net/manual/en/solrquery.setfacetmissing.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetOffset](https://www.php.net/manual/en/solrquery.setfacetoffset.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$offset`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetPrefix](https://www.php.net/manual/en/solrquery.setfacetprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$prefix`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setFacetSort](https://www.php.net/manual/en/solrquery.setfacetsort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$facetSort`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroup](https://www.php.net/manual/en/solrquery.setgroup.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupCachePercent](https://www.php.net/manual/en/solrquery.setgroupcachepercent.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$percent`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupFacet](https://www.php.net/manual/en/solrquery.setgroupfacet.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupFormat](https://www.php.net/manual/en/solrquery.setgroupformat.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupLimit](https://www.php.net/manual/en/solrquery.setgrouplimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupMain](https://www.php.net/manual/en/solrquery.setgroupmain.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupNGroups](https://www.php.net/manual/en/solrquery.setgroupngroups.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupOffset](https://www.php.net/manual/en/solrquery.setgroupoffset.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setGroupTruncate](https://www.php.net/manual/en/solrquery.setgrouptruncate.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlight](https://www.php.net/manual/en/solrquery.sethighlight.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightAlternateField](https://www.php.net/manual/en/solrquery.sethighlightalternatefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$field`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightFormatter](https://www.php.net/manual/en/solrquery.sethighlightformatter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$formatter`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightFragmenter](https://www.php.net/manual/en/solrquery.sethighlightfragmenter.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fragmenter`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightFragsize](https://www.php.net/manual/en/solrquery.sethighlightfragsize.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$size`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightHighlightMultiTerm](https://www.php.net/manual/en/solrquery.sethighlighthighlightmultiterm.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightMaxAlternateFieldLength](https://www.php.net/manual/en/solrquery.sethighlightmaxalternatefieldlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$fieldLength`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightmaxanalyzedchars.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightMergeContiguous](https://www.php.net/manual/en/solrquery.sethighlightmergecontiguous.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightQuery](https://www.php.net/manual/en/solrquery.sethighlightquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$q`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightRegexMaxAnalyzedChars](https://www.php.net/manual/en/solrquery.sethighlightregexmaxanalyzedchars.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxAnalyzedChars`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightRegexPattern](https://www.php.net/manual/en/solrquery.sethighlightregexpattern.php)([string](https://www.php.net/manual/en/language.types.string.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightRegexSlop](https://www.php.net/manual/en/solrquery.sethighlightregexslop.php)([float](https://www.php.net/manual/en/language.types.float.php) `$factor`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightRequireFieldMatch](https://www.php.net/manual/en/solrquery.sethighlightrequirefieldmatch.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightSimplePost](https://www.php.net/manual/en/solrquery.sethighlightsimplepost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$simplePost`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightSimplePre](https://www.php.net/manual/en/solrquery.sethighlightsimplepre.php)([string](https://www.php.net/manual/en/language.types.string.php) `$simplePre`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightSnippets](https://www.php.net/manual/en/solrquery.sethighlightsnippets.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`, [string](https://www.php.net/manual/en/language.types.string.php) `$field_override` = ?): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setHighlightUsePhraseHighlighter](https://www.php.net/manual/en/solrquery.sethighlightusephrasehighlighter.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMlt](https://www.php.net/manual/en/solrquery.setmlt.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltBoost](https://www.php.net/manual/en/solrquery.setmltboost.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltCount](https://www.php.net/manual/en/solrquery.setmltcount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$count`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMaxNumQueryTerms](https://www.php.net/manual/en/solrquery.setmltmaxnumqueryterms.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMaxNumTokens](https://www.php.net/manual/en/solrquery.setmltmaxnumtokens.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$value`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMaxWordLength](https://www.php.net/manual/en/solrquery.setmltmaxwordlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$maxWordLength`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMinDocFrequency](https://www.php.net/manual/en/solrquery.setmltmindocfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minDocFrequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMinTermFrequency](https://www.php.net/manual/en/solrquery.setmltmintermfrequency.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minTermFrequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setMltMinWordLength](https://www.php.net/manual/en/solrquery.setmltminwordlength.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$minWordLength`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setOmitHeader](https://www.php.net/manual/en/solrquery.setomitheader.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setQuery](https://www.php.net/manual/en/solrquery.setquery.php)([string](https://www.php.net/manual/en/language.types.string.php) `$query`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setRows](https://www.php.net/manual/en/solrquery.setrows.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$rows`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setShowDebugInfo](https://www.php.net/manual/en/solrquery.setshowdebuginfo.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setStart](https://www.php.net/manual/en/solrquery.setstart.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$start`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setStats](https://www.php.net/manual/en/solrquery.setstats.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTerms](https://www.php.net/manual/en/solrquery.setterms.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsField](https://www.php.net/manual/en/solrquery.settermsfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldname`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsIncludeLowerBound](https://www.php.net/manual/en/solrquery.settermsincludelowerbound.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsIncludeUpperBound](https://www.php.net/manual/en/solrquery.settermsincludeupperbound.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsLimit](https://www.php.net/manual/en/solrquery.settermslimit.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$limit`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsLowerBound](https://www.php.net/manual/en/solrquery.settermslowerbound.php)([string](https://www.php.net/manual/en/language.types.string.php) `$lowerBound`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsMaxCount](https://www.php.net/manual/en/solrquery.settermsmaxcount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsMinCount](https://www.php.net/manual/en/solrquery.settermsmincount.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$frequency`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsPrefix](https://www.php.net/manual/en/solrquery.settermsprefix.php)([string](https://www.php.net/manual/en/language.types.string.php) `$prefix`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsReturnRaw](https://www.php.net/manual/en/solrquery.settermsreturnraw.php)([bool](https://www.php.net/manual/en/language.types.boolean.php) `$flag`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsSort](https://www.php.net/manual/en/solrquery.settermssort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$sortType`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTermsUpperBound](https://www.php.net/manual/en/solrquery.settermsupperbound.php)([string](https://www.php.net/manual/en/language.types.string.php) `$upperBound`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

public[SolrQuery::setTimeAllowed](https://www.php.net/manual/en/solrquery.settimeallowed.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$timeAllowed`): [SolrQuery](https://www.php.net/manual/en/class.solrquery.php)

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrdismaxquery.php\#solrdismaxquery.constants)

**`[SolrDisMaxQuery::ORDER\_ASC](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.order-asc)`**

Used to specify that the sorting should be in acending order (Duplicated for easier migration)

**`[SolrDisMaxQuery::ORDER\_DESC](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.order-desc)`**

Used to specify that the sorting should be in descending order (Duplicated for easier migration)

**`[SolrDisMaxQuery::FACET\_SORT\_INDEX](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.facet-sort-index)`**

Used to specify that the facet should sort by index (Duplicated for easier migration)

**`[SolrDisMaxQuery::FACET\_SORT\_COUNT](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.facet-sort-count)`**

Used to specify that the facet should sort by count (Duplicated for easier migration)

**`[SolrDisMaxQuery::TERMS\_SORT\_INDEX](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.terms-sort-index)`**

Used in the TermsComponent (Duplicated for easier migration)

**`[SolrDisMaxQuery::TERMS\_SORT\_COUNT](https://www.php.net/manual/en/class.solrdismaxquery.php#solrdismaxquery.constants.terms-sort-count)`**

Used in the TermsComponent (Duplicated for easier migration)

## Table of Contents [¶](https://www.php.net/manual/en/class.solrdismaxquery.php\#class.solrdismaxquery)

- [SolrDisMaxQuery::addBigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.addbigramphrasefield.php) — Adds a Phrase Bigram Field (pf2 parameter)
- [SolrDisMaxQuery::addBoostQuery](https://www.php.net/manual/en/solrdismaxquery.addboostquery.php) — Adds a boost query field with value and optional boost (bq parameter)
- [SolrDisMaxQuery::addPhraseField](https://www.php.net/manual/en/solrdismaxquery.addphrasefield.php) — Adds a Phrase Field (pf parameter)
- [SolrDisMaxQuery::addQueryField](https://www.php.net/manual/en/solrdismaxquery.addqueryfield.php) — Add a query field with optional boost (qf parameter)
- [SolrDisMaxQuery::addTrigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.addtrigramphrasefield.php) — Adds a Trigram Phrase Field (pf3 parameter)
- [SolrDisMaxQuery::addUserField](https://www.php.net/manual/en/solrdismaxquery.adduserfield.php) — Adds a field to User Fields Parameter (uf)
- [SolrDisMaxQuery::\_\_construct](https://www.php.net/manual/en/solrdismaxquery.construct.php) — Class Constructor
- [SolrDisMaxQuery::removeBigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.removebigramphrasefield.php) — Removes phrase bigram field (pf2 parameter)
- [SolrDisMaxQuery::removeBoostQuery](https://www.php.net/manual/en/solrdismaxquery.removeboostquery.php) — Removes a boost query partial by field name (bq)
- [SolrDisMaxQuery::removePhraseField](https://www.php.net/manual/en/solrdismaxquery.removephrasefield.php) — Removes a Phrase Field (pf parameter)
- [SolrDisMaxQuery::removeQueryField](https://www.php.net/manual/en/solrdismaxquery.removequeryfield.php) — Removes a Query Field (qf parameter)
- [SolrDisMaxQuery::removeTrigramPhraseField](https://www.php.net/manual/en/solrdismaxquery.removetrigramphrasefield.php) — Removes a Trigram Phrase Field (pf3 parameter)
- [SolrDisMaxQuery::removeUserField](https://www.php.net/manual/en/solrdismaxquery.removeuserfield.php) — Removes a field from The User Fields Parameter (uf)
- [SolrDisMaxQuery::setBigramPhraseFields](https://www.php.net/manual/en/solrdismaxquery.setbigramphrasefields.php) — Sets Bigram Phrase Fields and their boosts (and slops) using pf2 parameter
- [SolrDisMaxQuery::setBigramPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setbigramphraseslop.php) — Sets Bigram Phrase Slop (ps2 parameter)
- [SolrDisMaxQuery::setBoostFunction](https://www.php.net/manual/en/solrdismaxquery.setboostfunction.php) — Sets a Boost Function (bf parameter)
- [SolrDisMaxQuery::setBoostQuery](https://www.php.net/manual/en/solrdismaxquery.setboostquery.php) — Directly Sets Boost Query Parameter (bq)
- [SolrDisMaxQuery::setMinimumMatch](https://www.php.net/manual/en/solrdismaxquery.setminimummatch.php) — Set Minimum "Should" Match (mm)
- [SolrDisMaxQuery::setPhraseFields](https://www.php.net/manual/en/solrdismaxquery.setphrasefields.php) — Sets Phrase Fields and their boosts (and slops) using pf2 parameter
- [SolrDisMaxQuery::setPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setphraseslop.php) — Sets the default slop on phrase queries (ps parameter)
- [SolrDisMaxQuery::setQueryAlt](https://www.php.net/manual/en/solrdismaxquery.setqueryalt.php) — Set Query Alternate (q.alt parameter)
- [SolrDisMaxQuery::setQueryPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.setqueryphraseslop.php) — Specifies the amount of slop permitted on phrase queries explicitly included in the user's query string (qf parameter)
- [SolrDisMaxQuery::setTieBreaker](https://www.php.net/manual/en/solrdismaxquery.settiebreaker.php) — Sets Tie Breaker parameter (tie parameter)
- [SolrDisMaxQuery::setTrigramPhraseFields](https://www.php.net/manual/en/solrdismaxquery.settrigramphrasefields.php) — Directly Sets Trigram Phrase Fields (pf3 parameter)
- [SolrDisMaxQuery::setTrigramPhraseSlop](https://www.php.net/manual/en/solrdismaxquery.settrigramphraseslop.php) — Sets Trigram Phrase Slop (ps3 parameter)
- [SolrDisMaxQuery::setUserFields](https://www.php.net/manual/en/solrdismaxquery.setuserfields.php) — Sets User Fields parameter (uf)
- [SolrDisMaxQuery::useDisMaxQueryParser](https://www.php.net/manual/en/solrdismaxquery.usedismaxqueryparser.php) — Switch QueryParser to be DisMax Query Parser
- [SolrDisMaxQuery::useEDisMaxQueryParser](https://www.php.net/manual/en/solrdismaxquery.useedismaxqueryparser.php) — Switch QueryParser to be EDisMax

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrdismaxquery.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrdismaxquery%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrdismaxquery&repo=en&redirect=https://www.php.net/manual/en/class.solrdismaxquery.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google