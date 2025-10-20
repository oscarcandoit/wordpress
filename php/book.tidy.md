---
url: https://www.php.net/manual/en/book.tidy.php
scraped_at: 2025-10-20T02:30:50.769Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Tidy [¶](https://www.php.net/manual/en/book.tidy.php\#book.tidy)

- [Introduction](https://www.php.net/manual/en/intro.tidy.php)
- [Installing/Configuring](https://www.php.net/manual/en/tidy.setup.php)
  - [Requirements](https://www.php.net/manual/en/tidy.requirements.php)
  - [Installation](https://www.php.net/manual/en/tidy.installation.php)
  - [Runtime Configuration](https://www.php.net/manual/en/tidy.configuration.php)
- [Predefined Constants](https://www.php.net/manual/en/tidy.constants.php)
- [Examples](https://www.php.net/manual/en/tidy.examples.php)
  - [Tidy example](https://www.php.net/manual/en/tidy.examples.basic.php)
- [tidy](https://www.php.net/manual/en/class.tidy.php) — The tidy class
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
- [tidyNode](https://www.php.net/manual/en/class.tidynode.php) — The tidyNode class
  - [tidyNode::\_\_construct](https://www.php.net/manual/en/tidynode.construct.php) — Private constructor to disallow direct instantiation
  - [tidyNode::getNextSibling](https://www.php.net/manual/en/tidynode.getnextsibling.php) — Returns the next sibling node of the current node
  - [tidyNode::getParent](https://www.php.net/manual/en/tidynode.getparent.php) — Returns the parent node of the current node
  - [tidyNode::getPreviousSibling](https://www.php.net/manual/en/tidynode.getprevioussibling.php) — Returns the previous sibling node of the current node
  - [tidyNode::hasChildren](https://www.php.net/manual/en/tidynode.haschildren.php) — Checks if a node has children
  - [tidyNode::hasSiblings](https://www.php.net/manual/en/tidynode.hassiblings.php) — Checks if a node has siblings
  - [tidyNode::isAsp](https://www.php.net/manual/en/tidynode.isasp.php) — Checks if this node is ASP
  - [tidyNode::isComment](https://www.php.net/manual/en/tidynode.iscomment.php) — Checks if a node represents a comment
  - [tidyNode::isHtml](https://www.php.net/manual/en/tidynode.ishtml.php) — Checks if a node is an element node
  - [tidyNode::isJste](https://www.php.net/manual/en/tidynode.isjste.php) — Checks if this node is JSTE
  - [tidyNode::isPhp](https://www.php.net/manual/en/tidynode.isphp.php) — Checks if a node is PHP
  - [tidyNode::isText](https://www.php.net/manual/en/tidynode.istext.php) — Checks if a node represents text (no markup)
- [Tidy Functions](https://www.php.net/manual/en/ref.tidy.php)
  - [ob\_tidyhandler](https://www.php.net/manual/en/function.ob-tidyhandler.php) — ob\_start callback function to repair the buffer
  - [tidy\_access\_count](https://www.php.net/manual/en/function.tidy-access-count.php) — Returns the Number of Tidy accessibility warnings encountered for specified document
  - [tidy\_config\_count](https://www.php.net/manual/en/function.tidy-config-count.php) — Returns the Number of Tidy configuration errors encountered for specified document
  - [tidy\_error\_count](https://www.php.net/manual/en/function.tidy-error-count.php) — Returns the Number of Tidy errors encountered for specified document
  - [tidy\_get\_output](https://www.php.net/manual/en/function.tidy-get-output.php) — Return a string representing the parsed tidy markup
  - [tidy\_warning\_count](https://www.php.net/manual/en/function.tidy-warning-count.php) — Returns the Number of Tidy warnings encountered for specified document

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/tidy/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.tidy%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.tidy&repo=en&redirect=https://www.php.net/manual/en/book.tidy.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=123608&page=book.tidy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=123608&page=book.tidy&vote=down "Vote down!")

7


[**_anon_**](https://www.php.net/manual/en/book.tidy.php#123608) [¶](https://www.php.net/manual/en/book.tidy.php#123608)

**6 years ago**

`Configuration options in [http://tidy.sourceforge.net/docs/quickref.html](http://tidy.sourceforge.net/docs/quickref.html) are obsoletes.
Actual configuration options are here:
[http://api.html-tidy.org/tidy/quickref\_5.0.0.html](http://api.html-tidy.org/tidy/quickref_5.0.0.html)`

[up](https://www.php.net/manual/vote-note.php?id=91162&page=book.tidy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=91162&page=book.tidy&vote=down "Vote down!")

1


[**_sirmonko at tapirpirates dot net_**](https://www.php.net/manual/en/book.tidy.php#91162) [¶](https://www.php.net/manual/en/book.tidy.php#91162)

**16 years ago**

`here are the configuration options for tidy:
[http://tidy.sourceforge.net/docs/quickref.html](http://tidy.sourceforge.net/docs/quickref.html)`

[up](https://www.php.net/manual/vote-note.php?id=129530&page=book.tidy&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129530&page=book.tidy&vote=down "Vote down!")

0


[**_gbirch at tech-tamer dot com_**](https://www.php.net/manual/en/book.tidy.php#129530) [¶](https://www.php.net/manual/en/book.tidy.php#129530)

**1 year ago**

`The address of the archive of configuration options has moved to: [https://api.html-tidy.org/](https://api.html-tidy.org/)`

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.tidy&repo=en&redirect=https://www.php.net/manual/en/book.tidy.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google