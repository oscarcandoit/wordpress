---
url: https://www.php.net/manual/en/class.solrdocument.php
scraped_at: 2025-10-20T02:37:14.039Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrDocument class [¶](https://www.php.net/manual/en/class.solrdocument.php\#class.solrdocument)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrdocument.php\#solrdocument.intro)

Represents a Solr document retrieved from a query response.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrdocument.php\#solrdocument.synopsis)

finalclass **SolrDocument**implements [ArrayAccess](https://www.php.net/manual/en/class.arrayaccess.php), [Iterator](https://www.php.net/manual/en/class.iterator.php), [Serializable](https://www.php.net/manual/en/class.serializable.php) {

/\\* Constants \*/

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_DEFAULT](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-default) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_ASC](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-asc) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_DESC](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-desc) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_NAME](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-name) = 1;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_VALUE\_COUNT](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-value-count) = 2;

const[int](https://www.php.net/manual/en/language.types.integer.php)[SORT\_FIELD\_BOOST\_VALUE](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-boost-value) = 4;

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrdocument.construct.php)()

public[addField](https://www.php.net/manual/en/solrdocument.addfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`, [string](https://www.php.net/manual/en/language.types.string.php) `$fieldValue`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[clear](https://www.php.net/manual/en/solrdocument.clear.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_clone](https://www.php.net/manual/en/solrdocument.clone.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[current](https://www.php.net/manual/en/solrdocument.current.php)(): [SolrDocumentField](https://www.php.net/manual/en/class.solrdocumentfield.php)

public[deleteField](https://www.php.net/manual/en/solrdocument.deletefield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[fieldExists](https://www.php.net/manual/en/solrdocument.fieldexists.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_get](https://www.php.net/manual/en/solrdocument.get.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [SolrDocumentField](https://www.php.net/manual/en/class.solrdocumentfield.php)

public[getChildDocuments](https://www.php.net/manual/en/solrdocument.getchilddocuments.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getChildDocumentsCount](https://www.php.net/manual/en/solrdocument.getchilddocumentscount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getField](https://www.php.net/manual/en/solrdocument.getfield.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [SolrDocumentField](https://www.php.net/manual/en/class.solrdocumentfield.php)

public[getFieldCount](https://www.php.net/manual/en/solrdocument.getfieldcount.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getFieldNames](https://www.php.net/manual/en/solrdocument.getfieldnames.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getInputDocument](https://www.php.net/manual/en/solrdocument.getinputdocument.php)(): [SolrInputDocument](https://www.php.net/manual/en/class.solrinputdocument.php)

public[hasChildDocuments](https://www.php.net/manual/en/solrdocument.haschilddocuments.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_isset](https://www.php.net/manual/en/solrdocument.isset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[key](https://www.php.net/manual/en/solrdocument.key.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[merge](https://www.php.net/manual/en/solrdocument.merge.php)([SolrDocument](https://www.php.net/manual/en/class.solrdocument.php) `$sourceDoc`, [bool](https://www.php.net/manual/en/language.types.boolean.php) `$overwrite` = **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[next](https://www.php.net/manual/en/solrdocument.next.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[offsetExists](https://www.php.net/manual/en/solrdocument.offsetexists.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[offsetGet](https://www.php.net/manual/en/solrdocument.offsetget.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [SolrDocumentField](https://www.php.net/manual/en/class.solrdocumentfield.php)

public[offsetSet](https://www.php.net/manual/en/solrdocument.offsetset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`, [string](https://www.php.net/manual/en/language.types.string.php) `$fieldValue`): [void](https://www.php.net/manual/en/language.types.void.php)

public[offsetUnset](https://www.php.net/manual/en/solrdocument.offsetunset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [void](https://www.php.net/manual/en/language.types.void.php)

public[reset](https://www.php.net/manual/en/solrdocument.reset.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[rewind](https://www.php.net/manual/en/solrdocument.rewind.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

public[serialize](https://www.php.net/manual/en/solrdocument.serialize.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[\_\_set](https://www.php.net/manual/en/solrdocument.set.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`, [string](https://www.php.net/manual/en/language.types.string.php) `$fieldValue`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[sort](https://www.php.net/manual/en/solrdocument.sort.php)([int](https://www.php.net/manual/en/language.types.integer.php) `$sortOrderBy`, [int](https://www.php.net/manual/en/language.types.integer.php) `$sortDirection` = SolrDocument::SORT\_ASC): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[toArray](https://www.php.net/manual/en/solrdocument.toarray.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[unserialize](https://www.php.net/manual/en/solrdocument.unserialize.php)([string](https://www.php.net/manual/en/language.types.string.php) `$serialized`): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_unset](https://www.php.net/manual/en/solrdocument.unset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$fieldName`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[valid](https://www.php.net/manual/en/solrdocument.valid.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[\_\_destruct](https://www.php.net/manual/en/solrdocument.destruct.php)()

}

## Predefined Constants [¶](https://www.php.net/manual/en/class.solrdocument.php\#solrdocument.constants)

**`[SolrDocument::SORT\_DEFAULT](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-default)`**

Default mode for sorting fields within the document.

**`[SolrDocument::SORT\_ASC](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-asc)`**

Sorts the fields in ascending order

**`[SolrDocument::SORT\_DESC](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-desc)`**

Sorts the fields in descending order

**`[SolrDocument::SORT\_FIELD\_NAME](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-name)`**

Sorts the fields by field name.

**`[SolrDocument::SORT\_FIELD\_VALUE\_COUNT](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-value-count)`**

Sorts the fields by number of values in each field.

**`[SolrDocument::SORT\_FIELD\_BOOST\_VALUE](https://www.php.net/manual/en/class.solrdocument.php#solrdocument.constants.sort-field-boost-value)`**

Sorts the fields by thier boost values.

## Table of Contents [¶](https://www.php.net/manual/en/class.solrdocument.php\#class.solrdocument)

- [SolrDocument::addField](https://www.php.net/manual/en/solrdocument.addfield.php) — Adds a field to the document
- [SolrDocument::clear](https://www.php.net/manual/en/solrdocument.clear.php) — Drops all the fields in the document
- [SolrDocument::\_\_clone](https://www.php.net/manual/en/solrdocument.clone.php) — Creates a copy of a SolrDocument object
- [SolrDocument::\_\_construct](https://www.php.net/manual/en/solrdocument.construct.php) — Constructor
- [SolrDocument::current](https://www.php.net/manual/en/solrdocument.current.php) — Retrieves the current field
- [SolrDocument::deleteField](https://www.php.net/manual/en/solrdocument.deletefield.php) — Removes a field from the document
- [SolrDocument::\_\_destruct](https://www.php.net/manual/en/solrdocument.destruct.php) — Destructor
- [SolrDocument::fieldExists](https://www.php.net/manual/en/solrdocument.fieldexists.php) — Checks if a field exists in the document
- [SolrDocument::\_\_get](https://www.php.net/manual/en/solrdocument.get.php) — Access the field as a property
- [SolrDocument::getChildDocuments](https://www.php.net/manual/en/solrdocument.getchilddocuments.php) — Returns an array of child documents (SolrDocument)
- [SolrDocument::getChildDocumentsCount](https://www.php.net/manual/en/solrdocument.getchilddocumentscount.php) — Returns the number of child documents
- [SolrDocument::getField](https://www.php.net/manual/en/solrdocument.getfield.php) — Retrieves a field by name
- [SolrDocument::getFieldCount](https://www.php.net/manual/en/solrdocument.getfieldcount.php) — Returns the number of fields in this document
- [SolrDocument::getFieldNames](https://www.php.net/manual/en/solrdocument.getfieldnames.php) — Returns an array of fields names in the document
- [SolrDocument::getInputDocument](https://www.php.net/manual/en/solrdocument.getinputdocument.php) — Returns a SolrInputDocument equivalent of the object
- [SolrDocument::hasChildDocuments](https://www.php.net/manual/en/solrdocument.haschilddocuments.php) — Checks whether the document has any child documents
- [SolrDocument::\_\_isset](https://www.php.net/manual/en/solrdocument.isset.php) — Checks if a field exists
- [SolrDocument::key](https://www.php.net/manual/en/solrdocument.key.php) — Retrieves the current key
- [SolrDocument::merge](https://www.php.net/manual/en/solrdocument.merge.php) — Merges source to the current SolrDocument
- [SolrDocument::next](https://www.php.net/manual/en/solrdocument.next.php) — Moves the internal pointer to the next field
- [SolrDocument::offsetExists](https://www.php.net/manual/en/solrdocument.offsetexists.php) — Checks if a particular field exists
- [SolrDocument::offsetGet](https://www.php.net/manual/en/solrdocument.offsetget.php) — Retrieves a field
- [SolrDocument::offsetSet](https://www.php.net/manual/en/solrdocument.offsetset.php) — Adds a field to the document
- [SolrDocument::offsetUnset](https://www.php.net/manual/en/solrdocument.offsetunset.php) — Removes a field
- [SolrDocument::reset](https://www.php.net/manual/en/solrdocument.reset.php) — Alias of SolrDocument::clear
- [SolrDocument::rewind](https://www.php.net/manual/en/solrdocument.rewind.php) — Resets the internal pointer to the beginning
- [SolrDocument::serialize](https://www.php.net/manual/en/solrdocument.serialize.php) — Used for custom serialization
- [SolrDocument::\_\_set](https://www.php.net/manual/en/solrdocument.set.php) — Adds another field to the document
- [SolrDocument::sort](https://www.php.net/manual/en/solrdocument.sort.php) — Sorts the fields in the document
- [SolrDocument::toArray](https://www.php.net/manual/en/solrdocument.toarray.php) — Returns an array representation of the document
- [SolrDocument::unserialize](https://www.php.net/manual/en/solrdocument.unserialize.php) — Custom serialization of SolrDocument objects
- [SolrDocument::\_\_unset](https://www.php.net/manual/en/solrdocument.unset.php) — Removes a field from the document
- [SolrDocument::valid](https://www.php.net/manual/en/solrdocument.valid.php) — Checks if the current position internally is still valid

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrdocument.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrdocument%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrdocument&repo=en&redirect=https://www.php.net/manual/en/class.solrdocument.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google