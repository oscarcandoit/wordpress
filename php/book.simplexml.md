---
url: https://www.php.net/manual/en/book.simplexml.php
scraped_at: 2025-10-20T02:33:29.878Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SimpleXML [¶](https://www.php.net/manual/en/book.simplexml.php\#book.simplexml)

- [Introduction](https://www.php.net/manual/en/intro.simplexml.php)
- [Installing/Configuring](https://www.php.net/manual/en/simplexml.setup.php)
  - [Requirements](https://www.php.net/manual/en/simplexml.requirements.php)
  - [Installation](https://www.php.net/manual/en/simplexml.installation.php)
- [Examples](https://www.php.net/manual/en/simplexml.examples.php)
  - [Basic SimpleXML usage](https://www.php.net/manual/en/simplexml.examples-basic.php)
  - [Dealing with XML errors](https://www.php.net/manual/en/simplexml.examples-errors.php)
- [SimpleXMLElement](https://www.php.net/manual/en/class.simplexmlelement.php) — The SimpleXMLElement class
  - [SimpleXMLElement::addAttribute](https://www.php.net/manual/en/simplexmlelement.addattribute.php) — Adds an attribute to the SimpleXML element
  - [SimpleXMLElement::addChild](https://www.php.net/manual/en/simplexmlelement.addchild.php) — Adds a child element to the XML node
  - [SimpleXMLElement::asXML](https://www.php.net/manual/en/simplexmlelement.asxml.php) — Return a well-formed XML string based on SimpleXML element
  - [SimpleXMLElement::attributes](https://www.php.net/manual/en/simplexmlelement.attributes.php) — Identifies an element's attributes
  - [SimpleXMLElement::children](https://www.php.net/manual/en/simplexmlelement.children.php) — Finds children of given node
  - [SimpleXMLElement::\_\_construct](https://www.php.net/manual/en/simplexmlelement.construct.php) — Creates a new SimpleXMLElement object
  - [SimpleXMLElement::count](https://www.php.net/manual/en/simplexmlelement.count.php) — Counts the children of an element
  - [SimpleXMLElement::current](https://www.php.net/manual/en/simplexmlelement.current.php) — Returns the current element
  - [SimpleXMLElement::getDocNamespaces](https://www.php.net/manual/en/simplexmlelement.getdocnamespaces.php) — Returns namespaces declared in document
  - [SimpleXMLElement::getName](https://www.php.net/manual/en/simplexmlelement.getname.php) — Gets the name of the XML element
  - [SimpleXMLElement::getNamespaces](https://www.php.net/manual/en/simplexmlelement.getnamespaces.php) — Returns namespaces used in document
  - [SimpleXMLElement::getChildren](https://www.php.net/manual/en/simplexmlelement.getchildren.php) — Returns the sub-elements of the current element
  - [SimpleXMLElement::hasChildren](https://www.php.net/manual/en/simplexmlelement.haschildren.php) — Checks whether the current element has sub elements
  - [SimpleXMLElement::key](https://www.php.net/manual/en/simplexmlelement.key.php) — Return current key
  - [SimpleXMLElement::next](https://www.php.net/manual/en/simplexmlelement.next.php) — Move to next element
  - [SimpleXMLElement::registerXPathNamespace](https://www.php.net/manual/en/simplexmlelement.registerxpathnamespace.php) — Creates a prefix/ns context for the next XPath query
  - [SimpleXMLElement::rewind](https://www.php.net/manual/en/simplexmlelement.rewind.php) — Rewind to the first element
  - [SimpleXMLElement::saveXML](https://www.php.net/manual/en/simplexmlelement.savexml.php) — Alias of SimpleXMLElement::asXML
  - [SimpleXMLElement::\_\_toString](https://www.php.net/manual/en/simplexmlelement.tostring.php) — Returns the string content
  - [SimpleXMLElement::valid](https://www.php.net/manual/en/simplexmlelement.valid.php) — Check whether the current element is valid
  - [SimpleXMLElement::xpath](https://www.php.net/manual/en/simplexmlelement.xpath.php) — Runs XPath query on XML data
- [SimpleXMLIterator](https://www.php.net/manual/en/class.simplexmliterator.php) — The SimpleXMLIterator class
- [SimpleXML Functions](https://www.php.net/manual/en/ref.simplexml.php)
  - [simplexml\_import\_dom](https://www.php.net/manual/en/function.simplexml-import-dom.php) — Get a SimpleXMLElement object from an XML or HTML node
  - [simplexml\_load\_file](https://www.php.net/manual/en/function.simplexml-load-file.php) — Interprets an XML file into an object
  - [simplexml\_load\_string](https://www.php.net/manual/en/function.simplexml-load-string.php) — Interprets a string of XML into an object

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/simplexml/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.simplexml%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.simplexml&repo=en&redirect=https://www.php.net/manual/en/book.simplexml.php)

### User Contributed Notes 15 notes

[up](https://www.php.net/manual/vote-note.php?id=105330&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=105330&page=book.simplexml&vote=down "Vote down!")

288


[**_soloman at textgrid dot com_**](https://www.php.net/manual/en/book.simplexml.php#105330) [¶](https://www.php.net/manual/en/book.simplexml.php#105330)

**14 years ago**

`Three line xml2array:
<?php
$xml = simplexml_load_string($xmlstring);
$json = json_encode($xml);
$array = json_decode($json,TRUE);
?>
Ta da!`

[up](https://www.php.net/manual/vote-note.php?id=87083&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=87083&page=book.simplexml&vote=down "Vote down!")

6


[**_QLeap_**](https://www.php.net/manual/en/book.simplexml.php#87083) [¶](https://www.php.net/manual/en/book.simplexml.php#87083)

**16 years ago**

`Storing SimpleXMLElement values in $_SESSION does not work. Saving the results as an object or individual elements of the object will result in the dreaded "Warning: session_start() [function.session-start]: Node no longer exists" error.
For example, this does not work:
    $xml  = new SimpleXMLElement($page);
    $country  = $xml->Response->Placemark->AddressDetails->Country->CountryNameCode;
    $_SESSION['country'] = $country;
This will work:
    $_SESSION['country'] = (string) $country;`

[up](https://www.php.net/manual/vote-note.php?id=88457&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=88457&page=book.simplexml&vote=down "Vote down!")

4


[**_oscargodson at gmail dot com_**](https://www.php.net/manual/en/book.simplexml.php#88457) [¶](https://www.php.net/manual/en/book.simplexml.php#88457)

**16 years ago**

`To add to what others have said, you can't directly put a $_GET or $_POST value into a variable then into an attribute using SimpleXML. You must first convert it to an integer.
This will NOT work
<?php
      $page_id = $_GET['id'];
      echo $xml->page[$page_id]
?>
You will get something like:
Notice: Trying to get property of non-object in /Applications/MAMP/htdocs/mysite/index.php on line 10
However, this WILL work and is much simpler then using (string) or other methods.
<?php
$page_id = intval($_GET['id']);
echo $xml->page[$page_id]
?>`

[up](https://www.php.net/manual/vote-note.php?id=108688&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=108688&page=book.simplexml&vote=down "Vote down!")

10


[**_xaviered at gmail dot com_**](https://www.php.net/manual/en/book.simplexml.php#108688) [¶](https://www.php.net/manual/en/book.simplexml.php#108688)

**13 years ago**

`Here is a recursive function that will convert a given SimpleXMLElement object into an array, preserving namespaces and attributes.
<?php
function xmlObjToArr($obj) {
        $namespace = $obj->getDocNamespaces(true);
        $namespace[NULL] = NULL;

        $children = array();
        $attributes = array();
        $name = strtolower((string)$obj->getName());

        $text = trim((string)$obj);
        if( strlen($text) <= 0 ) {
            $text = NULL;
        }

        // get info for all namespaces
        if(is_object($obj)) {
            foreach( $namespace as $ns=>$nsUrl ) {
                // atributes
                $objAttributes = $obj->attributes($ns, true);
                foreach( $objAttributes as $attributeName => $attributeValue ) {
                    $attribName = strtolower(trim((string)$attributeName));
                    $attribVal = trim((string)$attributeValue);
                    if (!empty($ns)) {
                        $attribName = $ns . ':' . $attribName;
                    }
                    $attributes[$attribName] = $attribVal;
                }

                // children
                $objChildren = $obj->children($ns, true);
                foreach( $objChildren as $childName=>$child ) {
                    $childName = strtolower((string)$childName);
                    if( !empty($ns) ) {
                        $childName = $ns.':'.$childName;
                    }
                    $children[$childName][] = xmlObjToArr($child);
                }
            }
        }

        return array(
            'name'=>$name,
            'text'=>$text,
            'attributes'=>$attributes,
            'children'=>$children
        );
    }
?>`

[up](https://www.php.net/manual/vote-note.php?id=84135&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84135&page=book.simplexml&vote=down "Vote down!")

5


[**_aalaap at gmail dot com_**](https://www.php.net/manual/en/book.simplexml.php#84135) [¶](https://www.php.net/manual/en/book.simplexml.php#84135)

**17 years ago**

`Here are two quick and dirty functions that use SimpleXML to detect if a feed xml is RSS or ATOM:
<?php
function is_rss($feedxml) {
    @$feed = new SimpleXMLElement($feedxml);
    if ($feed->channel->item) {
        return true;
    } else {
        return false;
    }
}
function is_atom($feedxml) {
    @$feed = new SimpleXMLElement($feedxml);
    if ($feed->entry) {
        return true;
    } else {
        return false;
    }
}
?>
The functions take in the full text feed (retrieved via cURL, for example) and return a true or a false based on the result.`

[up](https://www.php.net/manual/vote-note.php?id=110958&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=110958&page=book.simplexml&vote=down "Vote down!")

5


[**_whyme_**](https://www.php.net/manual/en/book.simplexml.php#110958) [¶](https://www.php.net/manual/en/book.simplexml.php#110958)

**12 years ago**

`Simple means simple.  If you know the structure and just want the value of a tag:
<?php
$xml = simplexml_load_file($xmlfile);
print $xml->City->Street->Address->HouseColor;
?>
Warning, numbers can come out as strings, empty elements like <HouseColor></HouseColor> come out as array(0)`

[up](https://www.php.net/manual/vote-note.php?id=95762&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=95762&page=book.simplexml&vote=down "Vote down!")

3


[**_mahmutta at gmail dot com_**](https://www.php.net/manual/en/book.simplexml.php#95762) [¶](https://www.php.net/manual/en/book.simplexml.php#95762)

**15 years ago**

`while using simple xml and get double or float int value from xml object for using math operations (+ * - / ) some errors happens on the operation, this is because of simple xml returns everythings to objects.
exmple;
<?php
$name = "somestring";
$size = 11.45;
$xml = '
<xml>
<name>somestring</name>
<size>11.45</size>
</xml>';

$xmlget = simplexml_load_string($xml)
echo $xml->size*2;    // 20  its false
// ($xml->size is an object (int)11 and  (45) )
// this is true
echo $size*2;            // 22.90
echo (float)$size*2;   // 22.90
?>`

[up](https://www.php.net/manual/vote-note.php?id=113348&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=113348&page=book.simplexml&vote=down "Vote down!")

3


[**_dkrnl at yandex dot ru_**](https://www.php.net/manual/en/book.simplexml.php#113348) [¶](https://www.php.net/manual/en/book.simplexml.php#113348)

**12 years ago**

`Wrapper XMLReader class, for simple SAX-reading huge xml:
[https://github.com/dkrnl/SimpleXMLReader](https://github.com/dkrnl/SimpleXMLReader)
Usage example: [http://github.com/dkrnl/SimpleXMLReader/blob/master/examples/example1.php](http://github.com/dkrnl/SimpleXMLReader/blob/master/examples/example1.php)
<?php
/**
* Simple XML Reader
*
* @license Public Domain
* @author Dmitry Pyatkov(aka dkrnl) <dkrnl@yandex.ru>
* @url [http://github.com/dkrnl/SimpleXMLReader](http://github.com/dkrnl/SimpleXMLReader)
*/
class SimpleXMLReader extends XMLReader
{
    /**
     * Callbacks
     *
     * @var array
     */
    protected $callback = array();
    /**
     * Add node callback
     *
     * @param  string   $name
     * @param  callback $callback
     * @param  integer  $nodeType
     * @return SimpleXMLReader
     */
    public function registerCallback($name, $callback, $nodeType = XMLREADER::ELEMENT)
    {
        if (isset($this->callback[$nodeType][$name])) {
            throw new Exception("Already exists callback $name($nodeType).");
        }
        if (!is_callable($callback)) {
            throw new Exception("Already exists parser callback $name($nodeType).");
        }
        $this->callback[$nodeType][$name] = $callback;
        return $this;
    }
    /**
     * Remove node callback
     *
     * @param  string  $name
     * @param  integer $nodeType
     * @return SimpleXMLReader
     */
    public function unRegisterCallback($name, $nodeType = XMLREADER::ELEMENT)
    {
        if (!isset($this->callback[$nodeType][$name])) {
            throw new Exception("Unknow parser callback $name($nodeType).");
        }
        unset($this->callback[$nodeType][$name]);
        return $this;
    }
    /**
     * Run parser
     *
     * @return void
     */
    public function parse()
    {
        if (empty($this->callback)) {
            throw new Exception("Empty parser callback.");
        }
        $continue = true;
        while ($continue && $this->read()) {
            if (isset($this->callback[$this->nodeType][$this->name])) {
                $continue = call_user_func($this->callback[$this->nodeType][$this->name], $this);
            }
        }
    }
    /**
     * Run XPath query on current node
     *
     * @param  string $path
     * @param  string $version
     * @param  string $encoding
     * @return array(SimpleXMLElement)
     */
    public function expandXpath($path, $version = "1.0", $encoding = "UTF-8")
    {
        return $this->expandSimpleXml($version, $encoding)->xpath($path);
    }
    /**
     * Expand current node to string
     *
     * @param  string $version
     * @param  string $encoding
     * @return SimpleXMLElement
     */
    public function expandString($version = "1.0", $encoding = "UTF-8")
    {
        return $this->expandSimpleXml($version, $encoding)->asXML();
    }
    /**
     * Expand current node to SimpleXMLElement
     *
     * @param  string $version
     * @param  string $encoding
     * @param  string $className
     * @return SimpleXMLElement
     */
    public function expandSimpleXml($version = "1.0", $encoding = "UTF-8", $className = null)
    {
        $element = $this->expand();
        $document = new DomDocument($version, $encoding);
        $node = $document->importNode($element, true);
        $document->appendChild($node);
        return simplexml_import_dom($node, $className);
    }
    /**
     * Expand current node to DomDocument
     *
     * @param  string $version
     * @param  string $encoding
     * @return DomDocument
     */
    public function expandDomDocument($version = "1.0", $encoding = "UTF-8")
    {
        $element = $this->expand();
        $document = new DomDocument($version, $encoding);
        $node = $document->importNode($element, true);
        $document->appendChild($node);
        return $document;
    }
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=103816&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=103816&page=book.simplexml&vote=down "Vote down!")

4


[**_streaver91 at gmail dot com_**](https://www.php.net/manual/en/book.simplexml.php#103816) [¶](https://www.php.net/manual/en/book.simplexml.php#103816)

**14 years ago**

`The BIGGEST differece between an XML and a PHP array is that in an XML file, the name of elements can be the same even if they are siblings, eg. "<pa><ch /><ch /><ch /></pa>", while in an PHP array, the key of which must be different.
I think the array structure developed by svdmeer can fit for XML, and fits well.
here is an example array converted from an xml file:
array(
"@tag"=>"name",
"@attr"=>array(
    "id"=>"1","class"=>"2")
"@text"=>"some text",
)
or if it has childrens, that can be:
array(
"@tag"=>"name",
"@attr"=>array(
    "id"=>"1","class"=>"2")
"@items"=>array(
    0=>array(
        "@tag"=>"name","@text"=>"some text"
    )
)
Also, I wrote a function that can change that array back to XML.
<?php
function array2XML($arr,$root) {
$xml = new SimpleXMLElement("<?xml version=\"1.0\" encoding=\"utf-8\" ?><{$root}></{$root}>");
$f = create_function('$f,$c,$a','
        foreach($a as $v) {
            if(isset($v["@text"])) {
                $ch = $c->addChild($v["@tag"],$v["@text"]);
            } else {
                $ch = $c->addChild($v["@tag"]);
                if(isset($v["@items"])) {
                    $f($f,$ch,$v["@items"]);
                }
            }
            if(isset($v["@attr"])) {
                foreach($v["@attr"] as $attr => $val) {
                    $ch->addAttribute($attr,$val);
                }
            }
        }');
$f($f,$xml,$arr);
return $xml->asXML();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=101063&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101063&page=book.simplexml&vote=down "Vote down!")

3


[**_philipp at strazny dot com_**](https://www.php.net/manual/en/book.simplexml.php#101063) [¶](https://www.php.net/manual/en/book.simplexml.php#101063)

**14 years ago**

`Here's a quick way to dump the nodeValues from SimpleXML into an array using the path to each nodeValue as key. The paths are compatible with e.g. DOMXPath. I use this when I need to update values externally (i.e. in code that doesn't know about the underlying xml). Then I use DOMXPath to find the node containing the original value and update it.
<?php
function XMLToArrayFlat($xml, &$return, $path='', $root=false)
{
    $children = array();
    if ($xml instanceof SimpleXMLElement) {
        $children = $xml->children();
        if ($root){ // we're at root
            $path .= '/'.$xml->getName();
        }
    }
    if ( count($children) == 0 ){
        $return[$path] = (string)$xml;
        return;
    }
    $seen=array();
    foreach ($children as $child => $value) {
        $childname = ($child instanceof SimpleXMLElement)?$child->getName():$child;
        if ( !isset($seen[$childname])){
            $seen[$childname]=0;
        }
        $seen[$childname]++;
        XMLToArrayFlat($value, $return, $path.'/'.$child.'['.$seen[$childname].']');
    }
}
?>
Use like this:
<?php
$xml = simplexml_load_string(...some xml string...);
$xmlarray = array(); // this will hold the flattened data
XMLToArrayFlat($xml, $xmlarray, '', true);
?>
You can also pull multiple files in one array:
<?php
foreach($files as $file){
    $xml = simplexml_load_file($file);
    XMLToArrayFlat($xml, $xmlarray, $file.':', true);
}
?>
The respective filename/path is thus prefixed to each key.`

[up](https://www.php.net/manual/vote-note.php?id=100981&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=100981&page=book.simplexml&vote=down "Vote down!")

1


[**_kristof at viewranger dot com_**](https://www.php.net/manual/en/book.simplexml.php#100981) [¶](https://www.php.net/manual/en/book.simplexml.php#100981)

**14 years ago**

`If you tried to load an XML file with this, but the CDATA parts were not loaded for some reason, is because you should do it this way:
$xml = simplexml_load_file($this->filename, 'SimpleXMLElement', LIBXML_NOCDATA);
This converts CDATA to String in the returning object.`

[up](https://www.php.net/manual/vote-note.php?id=101949&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=101949&page=book.simplexml&vote=down "Vote down!")

1


[**_phil at dier dot us_**](https://www.php.net/manual/en/book.simplexml.php#101949) [¶](https://www.php.net/manual/en/book.simplexml.php#101949)

**14 years ago**

`Here's a function I came up with to convert an associative array to XML.  Works for multidimensional arrays as well.
<?php
function assocArrayToXML($root_element_name,$ar)
{
    $xml = new SimpleXMLElement("<?xml version=\"1.0\"?><{$root_element_name}></{$root_element_name}>");
    $f = create_function('$f,$c,$a','
            foreach($a as $k=>$v) {
                if(is_array($v)) {
                    $ch=$c->addChild($k);
                    $f($f,$ch,$v);
                } else {
                    $c->addChild($k,$v);
                }
            }');
    $f($f,$xml,$ar);
    return $xml->asXML();
}
?>`

[up](https://www.php.net/manual/vote-note.php?id=96263&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=96263&page=book.simplexml&vote=down "Vote down!")

0


[**_emmanuel_**](https://www.php.net/manual/en/book.simplexml.php#96263) [¶](https://www.php.net/manual/en/book.simplexml.php#96263)

**15 years ago**

`dynamic sql in php using xml:
test.xml:
<?xml version="1.0" encoding="UTF-8"?>
<sql>
    <statement>
        SELECT * FROM USERS
        <call criteria="byId">WHERE id = %d</call>
        <call criteria="byUsername">WHERE username = "%s"</call>;
    </statement>
</sql>
index.php:
<?php
function callMe($param) {
    $search = array('byUsername' => 'dynsql');

    if (isset($search[$param[1]])) {
        return sprintf($param[2], $search[$param[1]]);
    }

    return "";
}
$xml = simplexml_load_file("test.xml");
$string = $xml->statement->asXML();
$string = preg_replace_callback('/<call criteria="(\w+)">(.*?)<\/call>/', 'callMe', $string);
$node = simplexml_load_string($string);
echo $node;
?>
obviously, this example can be improved [in your own code.]`

[up](https://www.php.net/manual/vote-note.php?id=119080&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=119080&page=book.simplexml&vote=down "Vote down!")

 -1


[**_oleg at mastak dot fi_**](https://www.php.net/manual/en/book.simplexml.php#119080) [¶](https://www.php.net/manual/en/book.simplexml.php#119080)

**9 years ago**

`Two lines xml2array:
<?php
$xml = simplexml_load_string($xmlstring);
$array = (array) $xml;
?>`

[up](https://www.php.net/manual/vote-note.php?id=90554&page=book.simplexml&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=90554&page=book.simplexml&vote=down "Vote down!")

0


[**_mail at kleineedv dot de_**](https://www.php.net/manual/en/book.simplexml.php#90554) [¶](https://www.php.net/manual/en/book.simplexml.php#90554)

**16 years ago**

`I had a problem with simplexml reading nodes from an xml file. It always return an SimpleXML-Object but not the text inside the node.
Example:
<?xml version="1.0" encoding="UTF-8"?>
<Test>
    <Id>123</Id>
</Test>
Reading this xml into a variable called $xml and then doing the following
<?php
$myId = $xml->Id;
?>
Did not return 123 in $myId, but instead I got a SimpleXMLElement Object.
The solution is simple, when you know it. Use explicit string conversion.
<?php
$myId = (string)$xml->Id;
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.simplexml&repo=en&redirect=https://www.php.net/manual/en/book.simplexml.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google