---
url: https://www.php.net/manual/en/class.tidy.php
scraped_at: 2025-10-20T02:40:27.421Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# The [tidy](https://www.php.net/manual/en/class.tidy.php) class [¶](https://www.php.net/manual/en/class.tidy.php\#class.tidy)

(PHP 5, PHP 7, PHP 8, PECL tidy >= 0.5.2)

## Introduction [¶](https://www.php.net/manual/en/class.tidy.php\#tidy.intro)

An HTML node in an HTML file, as detected by tidy.


## Class synopsis [¶](https://www.php.net/manual/en/class.tidy.php\#tidy.synopsis)

class **tidy**
{

/\\* Properties \*/

public?[string](https://www.php.net/manual/en/language.types.string.php)[$errorBuffer](https://www.php.net/manual/en/tidy.props.errorbuffer.php) = null;

public?[string](https://www.php.net/manual/en/language.types.string.php)[$value](https://www.php.net/manual/en/class.tidy.php#tidy.props.value) = null;

/\\* Methods \*/

public[\_\_construct](https://www.php.net/manual/en/tidy.construct.php)(

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$filename` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$useIncludePath` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**

)

public[body](https://www.php.net/manual/en/tidy.body.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[tidyNode](https://www.php.net/manual/en/class.tidynode.php)

public[cleanRepair](https://www.php.net/manual/en/tidy.cleanrepair.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[diagnose](https://www.php.net/manual/en/tidy.diagnose.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getConfig](https://www.php.net/manual/en/tidy.getconfig.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

public[getHtmlVer](https://www.php.net/manual/en/tidy.gethtmlver.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[getOpt](https://www.php.net/manual/en/tidy.getopt.php)([string](https://www.php.net/manual/en/language.types.string.php) `$option`): [string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php)\|[bool](https://www.php.net/manual/en/language.types.boolean.php)

public[getOptDoc](https://www.php.net/manual/en/tidy.getoptdoc.php)([string](https://www.php.net/manual/en/language.types.string.php) `$option`): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[getRelease](https://www.php.net/manual/en/tidy.getrelease.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[getStatus](https://www.php.net/manual/en/tidy.getstatus.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

public[head](https://www.php.net/manual/en/tidy.head.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[tidyNode](https://www.php.net/manual/en/class.tidynode.php)

public[html](https://www.php.net/manual/en/tidy.html.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[tidyNode](https://www.php.net/manual/en/class.tidynode.php)

public[isXhtml](https://www.php.net/manual/en/tidy.isxhtml.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[isXml](https://www.php.net/manual/en/tidy.isxml.php)(): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[parseFile](https://www.php.net/manual/en/tidy.parsefile.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$filename`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$useIncludePath` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**

): [bool](https://www.php.net/manual/en/language.types.boolean.php)

public[parseString](https://www.php.net/manual/en/tidy.parsestring.php)([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [bool](https://www.php.net/manual/en/language.types.boolean.php)

publicstatic[repairFile](https://www.php.net/manual/en/tidy.repairfile.php)(

[string](https://www.php.net/manual/en/language.types.string.php) `$filename`,

[array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[bool](https://www.php.net/manual/en/language.types.boolean.php) `$useIncludePath` = **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`**

): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

publicstatic[repairString](https://www.php.net/manual/en/tidy.repairstring.php)([string](https://www.php.net/manual/en/language.types.string.php) `$string`, [array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[null](https://www.php.net/manual/en/language.types.null.php) `$config` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**, [?](https://www.php.net/manual/en/language.types.null.php)[string](https://www.php.net/manual/en/language.types.string.php) `$encoding` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**): [string](https://www.php.net/manual/en/language.types.string.php)\|[false](https://www.php.net/manual/en/language.types.singleton.php)

public[root](https://www.php.net/manual/en/tidy.root.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[tidyNode](https://www.php.net/manual/en/class.tidynode.php)

}

## Properties [¶](https://www.php.net/manual/en/class.tidy.php\#tidy.props)

value

The HTML representation of the node, including the surrounding tags.

## Table of Contents [¶](https://www.php.net/manual/en/class.tidy.php\#class.tidy)

- [tidy::body](https://www.php.net/manual/en/tidy.body.php) — Returns a tidyNode object starting from the <body> tag of the tidy parse tree
- [tidy::cleanRepair](https://www.php.net/manual/en/tidy.cleanrepair.php) — Execute configured cleanup and repair operations on parsed markup
- [tidy::\_\_construct](https://www.php.net/manual/en/tidy.construct.php) — Constructs a new tidy object
- [tidy::diagnose](https://www.php.net/manual/en/tidy.diagnose.php) — Run configured diagnostics on parsed and repaired markup
- [tidy::$errorBuffer](https://www.php.net/manual/en/tidy.props.errorbuffer.php) — Return warnings and errors which occurred parsing the specified document
- [tidy::getConfig](https://www.php.net/manual/en/tidy.getconfig.php) — Get current Tidy configuration
- [tidy::getHtmlVer](https://www.php.net/manual/en/tidy.gethtmlver.php) — Get the Detected HTML version for the specified document
- [tidy::getOpt](https://www.php.net/manual/en/tidy.getopt.php) — Returns the value of the specified configuration option for the tidy document
- [tidy::getOptDoc](https://www.php.net/manual/en/tidy.getoptdoc.php) — Returns the documentation for the given option name
- [tidy::getRelease](https://www.php.net/manual/en/tidy.getrelease.php) — Get release date (version) for Tidy library
- [tidy::getStatus](https://www.php.net/manual/en/tidy.getstatus.php) — Get status of specified document
- [tidy::head](https://www.php.net/manual/en/tidy.head.php) — Returns a tidyNode object starting from the <head> tag of the tidy parse tree
- [tidy::html](https://www.php.net/manual/en/tidy.html.php) — Returns a tidyNode object starting from the <html> tag of the tidy parse tree
- [tidy::isXhtml](https://www.php.net/manual/en/tidy.isxhtml.php) — Indicates if the document is a XHTML document
- [tidy::isXml](https://www.php.net/manual/en/tidy.isxml.php) — Indicates if the document is a generic (non HTML/XHTML) XML document
- [tidy::parseFile](https://www.php.net/manual/en/tidy.parsefile.php) — Parse markup in file or URI
- [tidy::parseString](https://www.php.net/manual/en/tidy.parsestring.php) — Parse a document stored in a string
- [tidy::repairFile](https://www.php.net/manual/en/tidy.repairfile.php) — Repair a file and return it as a string
- [tidy::repairString](https://www.php.net/manual/en/tidy.repairstring.php) — Repair a string using an optionally provided configuration file
- [tidy::root](https://www.php.net/manual/en/tidy.root.php) — Returns a tidyNode object representing the root of the tidy parse tree

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/tidy/tidy.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.tidy%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.tidy&repo=en&redirect=https://www.php.net/manual/en/class.tidy.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google