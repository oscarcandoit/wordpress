---
url: https://www.php.net/manual/en/xsl.examples-errors.php
scraped_at: 2025-10-20T02:58:56.794Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Error handling with libxml error handling functions [¶](https://www.php.net/manual/en/xsl.examples-errors.php\#xsl.examples-errors)

libxml offers a number of functions for handling errors, which can be
employed to capture and deal with errors in XSLT processing.


**Example #1 fruits.xml**

A valid XML file.

```
<fruits>
 <fruit>Apple</fruit>
 <fruit>Banana</fruit>
 <fruit>Cherry</fruit>
</fruits>
```

**Example #2 fruits.xsl**

Contains an invalid select expression.

```
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
 <xsl:output method="html" encoding="utf-8" indent="no"/>
 <xsl:template match="fruits">
  <ul>
   <xsl:apply-templates/>
  </ul>
 </xsl:template>
 <xsl:template match="fruit">
  <li><xsl:value-of select="THIS IS A DELIBERATE ERROR!"/></li>
 </xsl:template>
</xsl:stylesheet>
```

**Example #3 Collating and printing errors**

The example below captures and displays libxml errors raised when calling
[XSLTProcessor::importStyleSheet()](https://www.php.net/manual/en/xsltprocessor.importstylesheet.php) with a
stylesheet containing an error.


`<?php
$xmldoc = new DOMDocument();
$xsldoc = new DOMDocument();
$xsl = new XSLTProcessor();
$xmldoc->loadXML('fruits.xml');
$xsldoc->loadXML('fruits.xsl');
libxml_use_internal_errors(true);
$result = $xsl->importStyleSheet($xsldoc);
if (!$result) {
    foreach (libxml_get_errors() as $error) {
        echo "Libxml error: {$error->message}\n";
    }
}
libxml_use_internal_errors(false);
if ($result) {
    echo $xsl->transformToXML($xmldoc);
}
?>`

The above example will output
something similar to:

```
Libxml error: Invalid expression

Libxml error: compilation error: file fruits.xsl line 9 element value-of
Libxml error: xsl:value-of : could not compile select expression 'THIS IS A DELIBERATE ERROR!'

```

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/xsl/examples.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fxsl.examples-errors%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=xsl.examples-errors&repo=en&redirect=https://www.php.net/manual/en/xsl.examples-errors.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google