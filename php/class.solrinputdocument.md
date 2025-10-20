---
url: https://www.php.net/manual/en/class.solrinputdocument.php
scraped_at: 2025-10-20T02:41:43.927Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrInputDocument class [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#class.solrinputdocument)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#solrinputdocument.intro)

This class represents a Solr document that is about to be submitted to the Solr index.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#solrinputdocument.synopsis)

finalclass **SolrInputDocument**
{

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_DEFAULT](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-default) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_ASC](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-asc) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_DESC](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-desc) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_NAME](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-name) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_VALUE\_COUNT](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-value-count) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_BOOST\_VALUE](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-boost-value) = 4;

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrinputdocument.construct.php)()

public[addChildDocument](https://www.php.net/manual/en/solrinputdocument.addchilddocument.php)([SolrInputDocument](https://www.php.net/manual/en/class.solrinputdocument.php) `$child`): [void](https://www.php.net/manual/en/language.types.void.php)

public[addChildDocuments](https://www.php.net/manual/en/solrinputdocument.addchilddocuments.php)([array](https://www.php.net/manual/en/language.types.array.php) `&$docs`): [void](https://www.php.net/manual/en/language.types.void.php)

public[addField](https://www.php.net/manual/en/solrinputdocument.addfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`, [string](https://www.php.net/manual/en/language.types.string.php) `$fieldValue`, [float](https://www.php.net/manual/en/language.types.float.php) `$fieldBoostValue` = 0.0): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[clear](https://www.php.net/manual/en/solrinputdocument.clear.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_clone](https://www.php.net/manual/en/solrinputdocument.clone.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[deleteField](https://www.php.net/manual/en/solrinputdocument.deletefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[fieldExists](https://www.php.net/manual/en/solrinputdocument.fieldexists.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getBoost](https://www.php.net/manual/en/solrinputdocument.getboost.php)(): [float](https://www.php.net/manual/en/language.types.float.php)

public[getChildDocuments](https://www.php.net/manual/en/solrinputdocument.getchilddocuments.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getChildDocumentsCount](https://www.php.net/manual/en/solrinputdocument.getchilddocumentscount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getField](https://www.php.net/manual/en/solrinputdocument.getfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [SolrDocumentField](https://www.php.net/manual/en/class.solrdocumentfield.php)

public[getFieldBoost](https://www.php.net/manual/en/solrinputdocument.getfieldboost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [float](https://www.php.net/manual/en/language.types.float.php)

public[getFieldCount](https://www.php.net/manual/en/solrinputdocument.getfieldcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[getFieldNames](https://www.php.net/manual/en/solrinputdocument.getfieldnames.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[hasChildDocuments](https://www.php.net/manual/en/solrinputdocument.haschilddocuments.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[merge](https://www.php.net/manual/en/solrinputdocument.merge.php)([SolrInputDocument](https://www.php.net/manual/en/class.solrinputdocument.php) `$sourceDoc`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$overwrite` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[reset](https://www.php.net/manual/en/solrinputdocument.reset.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[setBoost](https://www.php.net/manual/en/solrinputdocument.setboost.php)([float](https://www.php.net/manual/en/language.types.float.php) `$documentBoostValue`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[setFieldBoost](https://www.php.net/manual/en/solrinputdocument.setfieldboost.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`, [float](https://www.php.net/manual/en/language.types.float.php) `$fieldBoostValue`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sort](https://www.php.net/manual/en/solrinputdocument.sort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$sortOrderBy`, [int](https://www.php.net/manual/en/language.types.integer.php) `$sortDirection` = SolrInputDocument::SORT\_ASC): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[toArray](https://www.php.net/manual/en/solrinputdocument.toarray.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[\_\_destruct](https://www.php.net/manual/en/solrinputdocument.destruct.php)()

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#solrinputdocument.constants)

## SolrInputDocument Class Constants [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#solrinputdocument.constants.types)

**`[SolrInputDocument::SORT\_DEFAULT](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-default)`**

Sorts the fields in ascending order.

**`[SolrInputDocument::SORT\_ASC](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-asc)`**

Sorts the fields in ascending order.

**`[SolrInputDocument::SORT\_DESC](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-desc)`**

Sorts the fields in descending order.

**`[SolrInputDocument::SORT\_FIELD\_NAME](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-name)`**

Sorts the fields by name

**`[SolrInputDocument::SORT\_FIELD\_VALUE\_COUNT](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-value-count)`**

Sorts the fields by number of values.

**`[SolrInputDocument::SORT\_FIELD\_BOOST\_VALUE](https://www.php.net/manual/en/class.solrinputdocument.php#solrinputdocument.constants.sort-field-boost-value)`**

Sorts the fields by boost value.

## Table of Contents [¶](https://www.php.net/manual/en/class.solrinputdocument.php\#class.solrinputdocument)

- [SolrInputDocument::addChildDocument](https://www.php.net/manual/en/solrinputdocument.addchilddocument.php) — Adds a child document for block indexing
- [SolrInputDocument::addChildDocuments](https://www.php.net/manual/en/solrinputdocument.addchilddocuments.php) — Adds an array of child documents
- [SolrInputDocument::addField](https://www.php.net/manual/en/solrinputdocument.addfield.php) — Adds a field to the document
- [SolrInputDocument::clear](https://www.php.net/manual/en/solrinputdocument.clear.php) — Resets the input document
- [SolrInputDocument::\_\_clone](https://www.php.net/manual/en/solrinputdocument.clone.php) — Creates a copy of a SolrDocument
- [SolrInputDocument::\_\_construct](https://www.php.net/manual/en/solrinputdocument.construct.php) — Constructor
- [SolrInputDocument::deleteField](https://www.php.net/manual/en/solrinputdocument.deletefield.php) — Removes a field from the document
- [SolrInputDocument::\_\_destruct](https://www.php.net/manual/en/solrinputdocument.destruct.php) — Destructor
- [SolrInputDocument::fieldExists](https://www.php.net/manual/en/solrinputdocument.fieldexists.php) — Checks if a field exists
- [SolrInputDocument::getBoost](https://www.php.net/manual/en/solrinputdocument.getboost.php) — Retrieves the current boost value for the document
- [SolrInputDocument::getChildDocuments](https://www.php.net/manual/en/solrinputdocument.getchilddocuments.php) — Returns an array of child documents (SolrInputDocument)
- [SolrInputDocument::getChildDocumentsCount](https://www.php.net/manual/en/solrinputdocument.getchilddocumentscount.php) — Returns the number of child documents
- [SolrInputDocument::getField](https://www.php.net/manual/en/solrinputdocument.getfield.php) — Retrieves a field by name
- [SolrInputDocument::getFieldBoost](https://www.php.net/manual/en/solrinputdocument.getfieldboost.php) — Retrieves the boost value for a particular field
- [SolrInputDocument::getFieldCount](https://www.php.net/manual/en/solrinputdocument.getfieldcount.php) — Returns the number of fields in the document
- [SolrInputDocument::getFieldNames](https://www.php.net/manual/en/solrinputdocument.getfieldnames.php) — Returns an array containing all the fields in the document
- [SolrInputDocument::hasChildDocuments](https://www.php.net/manual/en/solrinputdocument.haschilddocuments.php) — Returns true if the document has any child documents
- [SolrInputDocument::merge](https://www.php.net/manual/en/solrinputdocument.merge.php) — Merges one input document into another
- [SolrInputDocument::reset](https://www.php.net/manual/en/solrinputdocument.reset.php) — Alias of SolrInputDocument::clear
- [SolrInputDocument::setBoost](https://www.php.net/manual/en/solrinputdocument.setboost.php) — Sets the boost value for this document
- [SolrInputDocument::setFieldBoost](https://www.php.net/manual/en/solrinputdocument.setfieldboost.php) — Sets the index-time boost value for a field
- [SolrInputDocument::sort](https://www.php.net/manual/en/solrinputdocument.sort.php) — Sorts the fields within the document
- [SolrInputDocument::toArray](https://www.php.net/manual/en/solrinputdocument.toarray.php) — Returns an array representation of the input document

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrinputdocument.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrinputdocument%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrinputdocument&repo=en&redirect=https://www.php.net/manual/en/class.solrinputdocument.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google