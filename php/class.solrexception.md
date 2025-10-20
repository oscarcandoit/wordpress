---
url: https://www.php.net/manual/en/class.solrexception.php
scraped_at: 2025-10-20T02:36:37.740Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The SolrException class [¶](https://www.php.net/manual/en/class.solrexception.php\#class.solrexception)

(PECL solr >= 0.9.2)

## Introduction [¶](https://www.php.net/manual/en/class.solrexception.php\#solrexception.intro)

This is the base class for all exception thrown by the Solr extension classes.


## Class synopsis [¶](https://www.php.net/manual/en/class.solrexception.php\#solrexception.synopsis)

class **SolrException**extends [Exception](https://www.php.net/manual/en/class.exception.php)
{

/\\* Properties \*/

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$sourceline](https://www.php.net/manual/en/class.solrexception.php#solrexception.props.sourceline);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$sourcefile](https://www.php.net/manual/en/class.solrexception.php#solrexception.props.sourcefile);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$zif\_name](https://www.php.net/manual/en/class.solrexception.php#solrexception.props.zif-name);

/\\* Inherited properties \*/

protected[string](https://www.php.net/manual/en/language.types.string.php)[$message](https://www.php.net/manual/en/class.exception.php#exception.props.message) = "";

private[string](https://www.php.net/manual/en/language.types.string.php)[$string](https://www.php.net/manual/en/class.exception.php#exception.props.string) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$code](https://www.php.net/manual/en/class.exception.php#exception.props.code);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$file](https://www.php.net/manual/en/class.exception.php#exception.props.file) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$line](https://www.php.net/manual/en/class.exception.php#exception.props.line);

private[array](https://www.php.net/manual/en/language.types.array.php)[$trace](https://www.php.net/manual/en/class.exception.php#exception.props.trace) = \[\];

private?[Throwable](https://www.php.net/manual/en/class.throwable.php)[$previous](https://www.php.net/manual/en/class.exception.php#exception.props.previous) = null;

/\\* Methods \*/

public[getInternalInfo](https://www.php.net/manual/en/solrexception.getinternalinfo.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

/\\* Inherited methods \*/

finalpublic[Exception::getMessage](https://www.php.net/manual/en/exception.getmessage.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Exception::getPrevious](https://www.php.net/manual/en/exception.getprevious.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[Throwable](https://www.php.net/manual/en/class.throwable.php)

finalpublic[Exception::getCode](https://www.php.net/manual/en/exception.getcode.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Exception::getFile](https://www.php.net/manual/en/exception.getfile.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Exception::getLine](https://www.php.net/manual/en/exception.getline.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Exception::getTrace](https://www.php.net/manual/en/exception.gettrace.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[Exception::getTraceAsString](https://www.php.net/manual/en/exception.gettraceasstring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[Exception::\_\_toString](https://www.php.net/manual/en/exception.tostring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

private[Exception::\_\_clone](https://www.php.net/manual/en/exception.clone.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

}

## Properties [¶](https://www.php.net/manual/en/class.solrexception.php\#solrexception.props)

sourceline

The line in c-space source file where exception was generated

sourcefile

The c-space source file where exception was generated

zif\_name

The c-space function where exception was generated

## Table of Contents [¶](https://www.php.net/manual/en/class.solrexception.php\#class.solrexception)

- [SolrException::getInternalInfo](https://www.php.net/manual/en/solrexception.getinternalinfo.php) — Returns internal information where the Exception was thrown

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/solr/solrexception.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.solrexception%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.solrexception&repo=en&redirect=https://www.php.net/manual/en/class.solrexception.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google