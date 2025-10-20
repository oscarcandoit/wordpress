---
url: https://www.php.net/manual/en/class.solrobject.php
scraped_at: 2025-10-20T02:39:16.021Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrObject class [¶](https://www.php.net/manual/en/class.solrobject.php\#class.solrobject)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrobject.php\#solrobject.intro)

This is an object whose properties can also by accessed using the array syntax. All its properties are read-only.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrobject.php\#solrobject.synopsis)

finalclass **SolrObject**implements [ArrayAccess](https://www.php.net/manual/en/class.arrayaccess.php) {

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/solrobject.construct.php)()

public[getPropertyNames](https://www.php.net/manual/en/solrobject.getpropertynames.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[offsetExists](https://www.php.net/manual/en/solrobject.offsetexists.php)([string](https://www.php.net/manual/en/language.types.string.php) `$property_name`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[offsetGet](https://www.php.net/manual/en/solrobject.offsetget.php)([string](https://www.php.net/manual/en/language.types.string.php) `$property_name`): [mixed](https://www.php.net/manual/en/language.types.mixed.php)

public[offsetSet](https://www.php.net/manual/en/solrobject.offsetset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$property_name`, [string](https://www.php.net/manual/en/language.types.string.php) `$property_value`): [void](https://www.php.net/manual/en/language.types.void.php)

public[offsetUnset](https://www.php.net/manual/en/solrobject.offsetunset.php)([string](https://www.php.net/manual/en/language.types.string.php) `$property_name`): [void](https://www.php.net/manual/en/language.types.void.php)

public[\_\_destruct](https://www.php.net/manual/en/solrobject.destruct.php)()

}

## Table of Contents [¶](https://www.php.net/manual/en/class.solrobject.php\#class.solrobject)

- [SolrObject::\_\_construct](https://www.php.net/manual/en/solrobject.construct.php) — Creates Solr object
- [SolrObject::\_\_destruct](https://www.php.net/manual/en/solrobject.destruct.php) — Destructor
- [SolrObject::getPropertyNames](https://www.php.net/manual/en/solrobject.getpropertynames.php) — Returns an array of all the names of the properties
- [SolrObject::offsetExists](https://www.php.net/manual/en/solrobject.offsetexists.php) — Checks if the property exists
- [SolrObject::offsetGet](https://www.php.net/manual/en/solrobject.offsetget.php) — Used to retrieve a property
- [SolrObject::offsetSet](https://www.php.net/manual/en/solrobject.offsetset.php) — Sets the value for a property
- [SolrObject::offsetUnset](https://www.php.net/manual/en/solrobject.offsetunset.php) — Unsets the value for the property

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrobject.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrobject%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrobject&repo=en&redirect=https://www.php.net/manual/en/class.solrobject.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google