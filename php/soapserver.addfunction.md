---
url: https://www.php.net/manual/en/soapserver.addfunction.php
scraped_at: 2025-10-20T02:48:34.228Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# SoapServer::addFunction

(PHP 5, PHP 7, PHP 8)

SoapServer::addFunction — Adds one or more functions to handle SOAP requests

### Description [¶](https://www.php.net/manual/en/soapserver.addfunction.php\#refsect1-soapserver.addfunction-description)

public**SoapServer::addFunction**([array](https://www.php.net/manual/en/language.types.array.php)\|[string](https://www.php.net/manual/en/language.types.string.php)\|[int](https://www.php.net/manual/en/language.types.integer.php) `$functions`): [void](https://www.php.net/manual/en/language.types.void.php)

Exports one or more functions for remote clients


### Parameters [¶](https://www.php.net/manual/en/soapserver.addfunction.php\#refsect1-soapserver.addfunction-parameters)

`functions`

To export one function, pass the function name into this parameter as
a string.


To export several functions, pass an array of function names.


To export all the functions, pass a special constant **`[SOAP\_FUNCTIONS\_ALL](https://www.php.net/manual/en/soap.constants.php#constant.soap-functions-all)`**.


> **Note**:
>
>
> `functions` must receive all input arguments in the same
> order as defined in the WSDL file (They should not receive any output parameters
> as arguments) and return one or more values. To return several values they must
> return an array with named output parameters.

### Return Values [¶](https://www.php.net/manual/en/soapserver.addfunction.php\#refsect1-soapserver.addfunction-returnvalues)

No value is returned.


### Examples [¶](https://www.php.net/manual/en/soapserver.addfunction.php\#refsect1-soapserver.addfunction-examples)

**Example #1 **SoapServer::addFunction()** example**

`<?php
function echoString($inputString)
{
    return $inputString;
}
$server->addFunction("echoString");
function echoTwoStrings($inputString1, $inputString2)
{
    return array("outputString1" => $inputString1,
                 "outputString2" => $inputString2);
}
$server->addFunction(array("echoString", "echoTwoStrings"));
$server->addFunction(SOAP_FUNCTIONS_ALL);
?>`

### See Also [¶](https://www.php.net/manual/en/soapserver.addfunction.php\#refsect1-soapserver.addfunction-seealso)

- [SoapServer::\_\_construct()](https://www.php.net/manual/en/soapserver.construct.php) \- SoapServer constructor
- [SoapServer::setClass()](https://www.php.net/manual/en/soapserver.setclass.php) \- Sets the class which handles SOAP requests

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/soap/soapserver/addfunction.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsoapserver.addfunction%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=soapserver.addfunction&repo=en&redirect=https://www.php.net/manual/en/soapserver.addfunction.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=78777&page=soapserver.addfunction&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=78777&page=soapserver.addfunction&vote=down "Vote down!")

11


[**_dotpointer at gmail dot com_**](https://www.php.net/manual/en/soapserver.addfunction.php#78777) [¶](https://www.php.net/manual/en/soapserver.addfunction.php#78777)

**17 years ago**

`Be careful with SOAP_FUNCTIONS_ALL, as it adds ALL availiable PHP functions to your server.
This can be a potential security threat, imagine clients doing this:
echo $client->file_get_contents("c:\\my files\\my_passwords.doc");
And voila, they have the contents of your file my_passwords.doc.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=soapserver.addfunction&repo=en&redirect=https://www.php.net/manual/en/soapserver.addfunction.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google