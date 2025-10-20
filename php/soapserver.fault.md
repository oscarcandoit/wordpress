---
url: https://www.php.net/manual/en/soapserver.fault.php
scraped_at: 2025-10-20T02:56:45.559Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SoapServer::fault

(PHP 5, PHP 7, PHP 8)

SoapServer::fault — Issue SoapServer fault indicating an error

### Description [¶](https://www.php.net/manual/en/soapserver.fault.php\#refsect1-soapserver.fault-description)

public**SoapServer::fault**(

[string](https://www.php.net/manual/en/language.types.string.php) `$code`,

[string](https://www.php.net/manual/en/language.types.string.php) `$string`,

[string](https://www.php.net/manual/en/language.types.string.php) `$actor` = "",

[mixed](https://www.php.net/manual/en/language.types.mixed.php) `$details` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**,

[string](https://www.php.net/manual/en/language.types.string.php) `$name` = ""

): [void](https://www.php.net/manual/en/language.types.void.php)

Sends a response to the client of the current request indicating an error.


> **Note**:
>
>
> This can only be called when handling a request.

### Parameters [¶](https://www.php.net/manual/en/soapserver.fault.php\#refsect1-soapserver.fault-parameters)

`code`

The error code to return


`string`

A brief description of the error


`actor`

A string identifying the actor that caused the fault.


`details`

More details of the fault


`name`

The name of the fault. This can be used to select a name from a WSDL file.


### Return Values [¶](https://www.php.net/manual/en/soapserver.fault.php\#refsect1-soapserver.fault-returnvalues)

No value is returned.


### See Also [¶](https://www.php.net/manual/en/soapserver.fault.php\#refsect1-soapserver.fault-seealso)

- [SoapFault::\_\_construct()](https://www.php.net/manual/en/soapfault.construct.php) \- SoapFault constructor

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/soap/soapserver/fault.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsoapserver.fault%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=soapserver.fault&repo=en&redirect=https://www.php.net/manual/en/soapserver.fault.php)

### User Contributed Notes 4 notes

[up](https://www.php.net/manual/vote-note.php?id=93420&page=soapserver.fault&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=93420&page=soapserver.fault&vote=down "Vote down!")

3


[**_Amr Mostafa_**](https://www.php.net/manual/en/soapserver.fault.php#93420) [¶](https://www.php.net/manual/en/soapserver.fault.php#93420)

**16 years ago**

`This function currently terminates execution as well, which may be undesirable. See: [http://bugs.php.net/bug.php?id=49513](http://bugs.php.net/bug.php?id=49513)`

[up](https://www.php.net/manual/vote-note.php?id=84480&page=soapserver.fault&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=84480&page=soapserver.fault&vote=down "Vote down!")

0


[**_Anonymous_**](https://www.php.net/manual/en/soapserver.fault.php#84480) [¶](https://www.php.net/manual/en/soapserver.fault.php#84480)

**17 years ago**

`If you use Adobe Flex, Flash or AIR as SOAP client and are unable to get the error message in case of a soap fault, upgrade to PHP 5.2.6.
Details in:
[http://bugs.php.net/bug.php?id=43507](http://bugs.php.net/bug.php?id=43507)`

[up](https://www.php.net/manual/vote-note.php?id=112365&page=soapserver.fault&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=112365&page=soapserver.fault&vote=down "Vote down!")

 -3


[**_christian at cmjdesign dot dk_**](https://www.php.net/manual/en/soapserver.fault.php#112365) [¶](https://www.php.net/manual/en/soapserver.fault.php#112365)

**12 years ago**

`hi,
to control the fault output one may do the following
/**
* mySoapServer class
*/
class mySoapServer extends SoapServer {
    public function __construct($wsdl, array $options = null) {
        parent::SoapServer($wsdl, $options);
    }
    public function fault ($code, $string, $actor = null, $details = null, $name = null) {
        throw new SoapFault($code, $string, $actor, $details, $name);
    }
}
Use:
try {
    $server = new mySoapServer(null, array('uri' => $_SERVER['REQUEST_URI']));
    $server->setClass('mySoapAPI');
    $server->handle();
} catch (SoapFault $exc) {
    echo $exc->getTraceAsString();
}
that how i did this,
hope iot can help some one.`

[up](https://www.php.net/manual/vote-note.php?id=107430&page=soapserver.fault&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=107430&page=soapserver.fault&vote=down "Vote down!")

 -5


[**_dub357 at gmail dot com_**](https://www.php.net/manual/en/soapserver.fault.php#107430) [¶](https://www.php.net/manual/en/soapserver.fault.php#107430)

**13 years ago**

`This function also sends a 500 response code back to the client with the request.
This was causing issues with an Apache Axis 1.2 client I had so I instead implemented by own fault handling:
<?php
header("Content-Type: text/xml");
header("Status: 200");
die("<SOAP-ENV:Envelope xmlns:SOAP-ENV=\\"http://schemas.xmlsoap.org/soap/envelope/\\">
<SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>500</faultcode>
      <faultstring>".$ex->getMessage())."</faultstring>
    </SOAP-ENV:Fault>
</SOAP-ENV:Body>
</SOAP-ENV:Envelope>");
?>`

[＋add a note](https://www.php.net/manual/add-note.php?sect=soapserver.fault&repo=en&redirect=https://www.php.net/manual/en/soapserver.fault.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google