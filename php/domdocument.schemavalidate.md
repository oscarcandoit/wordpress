---
url: https://www.php.net/manual/en/domdocument.schemavalidate.php
scraped_at: 2025-10-20T02:56:28.742Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# DOMDocument::schemaValidate

(PHP 5, PHP 7, PHP 8)

DOMDocument::schemaValidate —
Validates a document based on a schema. Only XML Schema 1.0 is supported.


### Description [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php\#refsect1-domdocument.schemavalidate-description)

public**DOMDocument::schemaValidate**([string](https://www.php.net/manual/en/language.types.string.php) `$filename`, [int](https://www.php.net/manual/en/language.types.integer.php) `$flags` = 0): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Validates a document based on the given schema file.


### Parameters [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php\#refsect1-domdocument.schemavalidate-parameters)

`filename`

The path to the schema.


`flags`

A bitmask of Libxml schema validation flags. Currently the only supported value is [LIBXML\_SCHEMA\_CREATE](https://www.php.net/manual/en/libxml.constants.php). Available since Libxml 2.6.14.


### Return Values [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php\#refsect1-domdocument.schemavalidate-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### See Also [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php\#refsect1-domdocument.schemavalidate-seealso)

- [DOMDocument::schemaValidateSource()](https://www.php.net/manual/en/domdocument.schemavalidatesource.php) \- Validates a document based on a schema
- [DOMDocument::relaxNGValidate()](https://www.php.net/manual/en/domdocument.relaxngvalidate.php) \- Performs relaxNG validation on the document
- [DOMDocument::relaxNGValidateSource()](https://www.php.net/manual/en/domdocument.relaxngvalidatesource.php) \- Performs relaxNG validation on the document
- [DOMDocument::validate()](https://www.php.net/manual/en/domdocument.validate.php) \- Validates the document based on its DTD

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/dom/domdocument/schemavalidate.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdomdocument.schemavalidate%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=domdocument.schemavalidate&repo=en&redirect=https://www.php.net/manual/en/domdocument.schemavalidate.php)

### User Contributed Notes 6 notes

[up](https://www.php.net/manual/vote-note.php?id=62032&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=62032&page=domdocument.schemavalidate&vote=down "Vote down!")

37


[**_Mike A._**](https://www.php.net/manual/en/domdocument.schemavalidate.php#62032) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#62032)

**19 years ago**

`For more detailed feedback from DOMDocument::schemaValidate, disable libxml errors and fetch error information yourself.  See [http://php.net/manual/en/ref.libxml.php](http://php.net/manual/en/ref.libxml.php) for more info.
example.xml
<?xml version="1.0"?>
<example>
    <child_string>This is an example.</child_string>
    <child_integer>Error condition.</child_integer>
</example>
example.xsd
<?xml version="1.0"?>
<xs:schema xmlns:xs=" [http://www.w3.org/2001/XMLSchema](http://www.w3.org/2001/XMLSchema)"
elementFormDefault="qualified">
    <xs:element name="example">
        <xs:complexType>
            <xs:sequence>
                <xs:element name="child_string" type="xs:string"/>
                <xs:element name="child_integer" type="xs:integer"/>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
<?php
function libxml_display_error($error)
{
    $return = "<br/>\n";
    switch ($error->level) {
        case LIBXML_ERR_WARNING:
            $return .= "<b>Warning $error->code</b>: ";
            break;
        case LIBXML_ERR_ERROR:
            $return .= "<b>Error $error->code</b>: ";
            break;
        case LIBXML_ERR_FATAL:
            $return .= "<b>Fatal Error $error->code</b>: ";
            break;
    }
    $return .= trim($error->message);
    if ($error->file) {
        $return .=    " in <b>$error->file</b>";
    }
    $return .= " on line <b>$error->line</b>\n";
    return $return;
}
function libxml_display_errors() {
    $errors = libxml_get_errors();
    foreach ($errors as $error) {
        print libxml_display_error($error);
    }
    libxml_clear_errors();
}
// Enable user error handling
libxml_use_internal_errors(true);
$xml = new DOMDocument();
$xml->load('example.xml');
if (!$xml->schemaValidate('example.xsd')) {
    print '<b>DOMDocument::schemaValidate() Generated Errors!</b>';
    libxml_display_errors();
}
?>
Old error message:
Warning: DOMDocument::schemaValidate() [function.schemaValidate]: Element 'child_integer': 'Error condition.' is not a valid value of the atomic type 'xs:integer'. in example.php on line 40
New error message:
DOMDocument::schemaValidate() Generated Errors!
Error 1824: Element 'child_integer': 'Error condition.' is not a valid value of the atomic type 'xs:integer'. in example.xml on line 4`

[up](https://www.php.net/manual/vote-note.php?id=89893&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=89893&page=domdocument.schemavalidate&vote=down "Vote down!")

11


[**_NetPanther_**](https://www.php.net/manual/en/domdocument.schemavalidate.php#89893) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#89893)

**16 years ago**

`Initial situation:
- Debian Lenny
- Apache 2 with PHP 5.2.6
- libxml 2.6.32
Problem: While trying to validate a manually created (!) DOMDocument against an existing XML Schema, I ran into a warning like the one below. Validation fails, even though the document IS valid and the command line tool xmllint confirms this (even with libxml 2.6.32, so this must be a problem with DOM). The validation works fine with libxml 2.7.3.
Warning: DOMDocument::schemaValidate() [domdocument.schemavalidate]: Element 'YourRootElementName': No matching global declaration available for the validation root. in /var/www/YourFile.php on line X
Solution: As libxml 2.7.3 is not provided for Debian Lenny yet and this problem seems to be caused by DOM (s.o.), I currently use the following workaround on my machines. DOM obviously has some namespace problems with documents, that have been created manually (i.e. they were not loaded from a file).
So my workaround is saving the DOMDocument temporarily, re-loading it and then validating the temporary DOMDocument. Strangely enough the validation of the same document (= same content) now works. Sure, creating a temporary file is not a nice solution, but unless this bug is fixed, this workaround should do just fine.
<?php
// Works with libxml 2.7.3 and higher.
public function isValid()
{
return $this->dom->schemaValidate('schema.xsd');
}
// Workaround for prior libxml versions, e.g. 2.6.32.
public function isValid()
{
// Create temporary file and save manually created DOMDocument.
$tempFile = time() . '-' . rand() . '-document.tmp';
$this->dom->save($tempFile);

// Create temporary DOMDocument and re-load content from file.
$tempDom = new DOMDocument();
$tempDom->load($tempFile);

// Delete temporary file.
if (is_file($tempFile))
{
    unlink($tempFile);
}

// Validate temporary DOMDocument.
return $tempDom->schemaValidate('schema.xsd');
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=117995&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=117995&page=domdocument.schemavalidate&vote=down "Vote down!")

6


[**_mmamsch at googlemail dot com_**](https://www.php.net/manual/en/domdocument.schemavalidate.php#117995) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#117995)

**10 years ago**

`A note for people trying to validate complex schemas with PHP.  It seems that libxml will not automatically try to import referenced schemas, but simply skip the validation if the schemas were not explicitly imported.
In our example we tried to validate an XML file against a schema with the namespace "xttp://automotive-his.de/200706/rif" that contains a reference to the namespace "xttp://automotive-his.de/200706/rif-xhtml":
<xsd:complexType name="XHTML-CONTENT">
    <xsd:sequence>
      <xsd:any namespace="xttp://automotive-his.de/200706/rif-xhtml"/>
    </xsd:sequence>
</xsd:complexType>
which basically says that an xhtml-content element can contain any element from the rif-xhtml namespace.
However since libxml does not know where to find the schema file, it will stop the validation if the elements from the referenced namespace, passing also document with invalid xhtml content as valid.
The solution was to create a combined schema, which contains import statements for all files matching the referenced schemas:
<xsd:schema xmlns:xs="xttp://www.w3.org/2001/XMLSchema">
<xs:import namespace="xttp://automotive-his.de/200706/rif-xhtml" schemaLocation="rif-xhtml.xsd"/>
<xs:import namespace="xttp://automotive-his.de/200706/rif" schemaLocation="rif.xsd"/>
<xs:import namespace="xttp://www.w3.org/XML/1998/namespace" schemaLocation="../xml.xsd"/>
</xsd:schema>
Note that the schemaLocation tells the validator, where to find the files for the corresponding namespaces. When validating the XML document against this combined schema, libxml validated correctly the content inside the XHTML-Content.
Hope this helps someone out there.`

[up](https://www.php.net/manual/vote-note.php?id=81068&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=81068&page=domdocument.schemavalidate&vote=down "Vote down!")

3


[**_poletto at jeuxvideo dot com_**](https://www.php.net/manual/en/domdocument.schemavalidate.php#81068) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#81068)

**17 years ago**

`I had a tricky issue using this method, i thought it was bug but i realized i misundestood something about namespaces.
When you want to use a schema to describe an xml document, you basically put the default namespace to a personnal namespace (and you refer to this namespace in the targetNamespace attribute of your schema).
<?xml version="1.0" encoding="utf-8"?>
<root xmlns=" [http://my.uri.net](http://my.uri.net/)">
<elt>
    <x>blabla</x>
    <y>blabla</y>
</elt>
</root>
That xmlns attribute specifies a "default namespace" and means that the root element and its children are in this namespace.
What i misunderstood is that, there's no way with the DOM api to specify a "default namespace" for each children of the root element.
Thus you may need to use createElementNS() and createAttributeNS() methods for each created element or attribute in the document specifying the URI of your namespace each time (" [http://my.uri.net](http://my.uri.net/)").
This only applies if you want to validate a document built with the API, not with a document loaded from an xml file or stream.`

[up](https://www.php.net/manual/vote-note.php?id=71014&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=71014&page=domdocument.schemavalidate&vote=down "Vote down!")

 -1


[**_justin at redwiredesign dot com_**](https://www.php.net/manual/en/domdocument.schemavalidate.php#71014) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#71014)

**18 years ago**

`In his previous comment, Mike A wrote about validating documents using an XSD. However, you can validate without one. In my case, I needed to ensure that the content entered was just valid XML or not, and I couldn't find an XSD to support that. So I wrote this:
public static function validate($xml)
{
    libxml_use_internal_errors(true);
    $doc = new DOMDocument('1.0', 'utf-8');
    $doc->loadXML($xml);
    $errors = libxml_get_errors();
    if (empty($errors))
    {
        return true;
    }
    $error = $errors[0];
    if ($error->level < 3)
    {
        return true;
    }
    $lines = explode("\r", $xml);
    $line = $lines[($error->line)-1];
    $message = $error->message.' at line '.$error->line.':<br />'.htmlentities($line);
    return $message;
}
The catch here is that the function only checks for the first error is LIBXML_ERR_FATAL, which would break XSL/XML compilation.
In my experience, the errors are returned by libxml_get_errors in descending severity, so this may be an OK thing to do.`

[up](https://www.php.net/manual/vote-note.php?id=101782&page=domdocument.schemavalidate&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101782&page=domdocument.schemavalidate&vote=down "Vote down!")

 -2


[**_wkoehler at ce-gmbh dot com_**](https://www.php.net/manual/en/domdocument.schemavalidate.php#101782) [¶](https://www.php.net/manual/en/domdocument.schemavalidate.php#101782)

**14 years ago**

`In older versions of PHP5 this function might cause error messages when dealing with namespaces. I had problems with PHP 5.2.14 which comes with libXML V2.6.16. After switching to PHP 5.3.5 with libXML V2.7.7 I no longer had problems. Took me only about 30 hrs to figure that one out.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=domdocument.schemavalidate&repo=en&redirect=https://www.php.net/manual/en/domdocument.schemavalidate.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google