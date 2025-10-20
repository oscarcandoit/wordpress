---
url: https://www.php.net/manual/en/class.parseerror.php
scraped_at: 2025-10-20T02:35:37.913Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# ParseError [¶](https://www.php.net/manual/en/class.parseerror.php\#class.parseerror)

(PHP 7, PHP 8)

## Introduction [¶](https://www.php.net/manual/en/class.parseerror.php\#parseerror.intro)

**ParseError** is thrown when an
error occurs while parsing PHP code, such as when
[eval()](https://www.php.net/manual/en/function.eval.php) is called.


> **Note**:
> **ParseError** extends [CompileError](https://www.php.net/manual/en/class.compileerror.php)
> as of PHP 7.3.0. Formerly, it extended [Error](https://www.php.net/manual/en/class.error.php).

## Class synopsis [¶](https://www.php.net/manual/en/class.parseerror.php\#parseerror.synopsis)

class **ParseError** extends [CompileError](https://www.php.net/manual/en/class.compileerror.php)
{

/\\* Inherited properties \*/

protected[string](https://www.php.net/manual/en/language.types.string.php)[$message](https://www.php.net/manual/en/class.error.php#error.props.message) = "";

private[string](https://www.php.net/manual/en/language.types.string.php)[$string](https://www.php.net/manual/en/class.error.php#error.props.string) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$code](https://www.php.net/manual/en/class.error.php#error.props.code);

protected[string](https://www.php.net/manual/en/language.types.string.php)[$file](https://www.php.net/manual/en/class.error.php#error.props.file) = "";

protected[int](https://www.php.net/manual/en/language.types.integer.php)[$line](https://www.php.net/manual/en/class.error.php#error.props.line);

private[array](https://www.php.net/manual/en/language.types.array.php)[$trace](https://www.php.net/manual/en/class.error.php#error.props.trace) = \[\];

private?[Throwable](https://www.php.net/manual/en/class.throwable.php)[$previous](https://www.php.net/manual/en/class.error.php#error.props.previous) = null;

/\\* Inherited methods \*/

public[Error::\_\_construct](https://www.php.net/manual/en/error.construct.php)([string](https://www.php.net/manual/en/language.types.string.php) `$message` = "", [int](https://www.php.net/manual/en/language.types.integer.php) `$code` = 0, [?](https://www.php.net/manual/en/language.types.null.php)[Throwable](https://www.php.net/manual/en/class.throwable.php) `$previous` = **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`**)

finalpublic[Error::getMessage](https://www.php.net/manual/en/error.getmessage.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Error::getPrevious](https://www.php.net/manual/en/error.getprevious.php)(): [?](https://www.php.net/manual/en/language.types.null.php)[Throwable](https://www.php.net/manual/en/class.throwable.php)

finalpublic[Error::getCode](https://www.php.net/manual/en/error.getcode.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Error::getFile](https://www.php.net/manual/en/error.getfile.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

finalpublic[Error::getLine](https://www.php.net/manual/en/error.getline.php)(): [int](https://www.php.net/manual/en/language.types.integer.php)

finalpublic[Error::getTrace](https://www.php.net/manual/en/error.gettrace.php)(): [array](https://www.php.net/manual/en/language.types.array.php)

finalpublic[Error::getTraceAsString](https://www.php.net/manual/en/error.gettraceasstring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

public[Error::\_\_toString](https://www.php.net/manual/en/error.tostring.php)(): [string](https://www.php.net/manual/en/language.types.string.php)

private[Error::\_\_clone](https://www.php.net/manual/en/error.clone.php)(): [void](https://www.php.net/manual/en/language.types.void.php)

}

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/predefined/parseerror.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fclass.parseerror%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.parseerror&repo=en&redirect=https://www.php.net/manual/en/class.parseerror.php)

### User Contributed Notes 2 notes

[up](https://www.php.net/manual/vote-note.php?id=128192&page=class.parseerror&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128192&page=class.parseerror&vote=down "Vote down!")

0


[**_SixPigPigWikiSix_**](https://www.php.net/manual/en/class.parseerror.php#128192) [¶](https://www.php.net/manual/en/class.parseerror.php#128192)

**2 years ago**

`The priority of Parse Error should be higher than that of Fatal Error,Parse Error, which has the highest priority among all PHP exceptions. See the following example:
<?php
error_reporting(E_ALL);
test()
//System output a parse error
?>
<?php
error_reporting(E_WARNING);
test()
//System output a parse error
?>
<?php
error_reporting(E_ERROR);
test()
//System output a parse error
?>
<?php
error_reporting(E_PARSE);
test()
//System output a parse error
?>`

[up](https://www.php.net/manual/vote-note.php?id=124423&page=class.parseerror&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=124423&page=class.parseerror&vote=down "Vote down!")

 -2


[**_andrian dot test dot job at gmail dot com_**](https://www.php.net/manual/en/class.parseerror.php#124423) [¶](https://www.php.net/manual/en/class.parseerror.php#124423)

**5 years ago**

`<?php
/*
* The function eval() evaluate his argument as an instruction PHP
* Then the argument must respect the standar of PHP codage
* In this example the semicolon are missign
*/
try{
    eval("echo 'toto' echo 'tata'");
}catch(ParseError $p){
    echo $p->getMessage();
}
/*
* If you run this code the result is different of the result of above code
* PHP will output the standar parse Error: syntax error, ....
*
eval("echo 'toto' echo 'tata'");
*/`

[＋add a note](https://www.php.net/manual/add-note.php?sect=class.parseerror&repo=en&redirect=https://www.php.net/manual/en/class.parseerror.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google