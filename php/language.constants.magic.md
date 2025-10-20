---
url: https://www.php.net/manual/en/language.constants.magic.php
scraped_at: 2025-10-20T02:41:20.466Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Magic constants [¶](https://www.php.net/manual/en/language.constants.magic.php\#language.constants.magic)

There are a few magical constants that change depending on
where they are used. For example, the value of
**`[\_\_LINE\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.line)`** depends on the line that it's
used on in a script. All these "magical" constants are resolved
at compile time, unlike regular constants, which are resolved at runtime.
These special constants are case-insensitive and are as follows:


| Name | Description |
| --- | --- |
| **`[\_\_LINE\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.line)`** | The current line number of the file. |
| **`[\_\_FILE\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.file)`** | The full path and filename of the file with symlinks resolved. If used inside an include,<br> the name of the included file is returned. |
| **`[\_\_DIR\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.dir)`** | The directory of the file. If used inside an include,<br> the directory of the included file is returned. This is equivalent<br> to `dirname(__FILE__)`. This directory name<br> does not have a trailing slash unless it is the root directory. |
| **`[\_\_FUNCTION\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.function)`** | The function name, or `{closure}` for anonymous functions. |
| **`[\_\_CLASS\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.class)`** | The class name. The class name includes the namespace<br> it was declared in (e.g. `Foo\Bar`).<br> When used inside a trait method,<br> **`[\_\_CLASS\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.class)`** is the name of the class the trait<br> is used in. |
| **`[\_\_TRAIT\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.trait)`** | The trait name. The trait name includes the namespace<br> it was declared in (e.g. `Foo\Bar`). |
| **`[\_\_METHOD\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.method)`** | The class method name. |
| **`[\_\_PROPERTY\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.property)`** | Only valid inside a<br> [property hook](https://www.php.net/manual/en/language.oop5.property-hooks.php).<br> It is equal to the name of the property. |
| **`[\_\_NAMESPACE\_\_](https://www.php.net/manual/en/language.constants.magic.php#constant.namespace)`** | The name of the current namespace. |
| **`ClassName::class`** | The fully qualified class name. |

**PHP's magic constants**

### See Also

- [::class](https://www.php.net/manual/en/language.oop5.basic.php#language.oop5.basic.class.class)
- [get\_class()](https://www.php.net/manual/en/function.get-class.php)
- [get\_object\_vars()](https://www.php.net/manual/en/function.get-object-vars.php)
- [file\_exists()](https://www.php.net/manual/en/function.file-exists.php)
- [function\_exists()](https://www.php.net/manual/en/function.function-exists.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/constants.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.constants.magic%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants.magic&repo=en&redirect=https://www.php.net/manual/en/language.constants.magic.php)

### User Contributed Notes 3 notes

[up](https://www.php.net/manual/vote-note.php?id=128527&page=language.constants.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128527&page=language.constants.magic&vote=down "Vote down!")

7


[**_chris at ocproducts dot com_**](https://www.php.net/manual/en/language.constants.magic.php#128527) [¶](https://www.php.net/manual/en/language.constants.magic.php#128527)

**2 years ago**

`Note that __CLASS__ and __METHOD__ both reference the class the code is written in, not whatever the object class is. E.g. if you have an object of class B inheriting from class A, any usage of __CLASS__ in class A is going to give "A".`

[up](https://www.php.net/manual/vote-note.php?id=127252&page=language.constants.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=127252&page=language.constants.magic&vote=down "Vote down!")

4


[**_theking2 at king dot ma_**](https://www.php.net/manual/en/language.constants.magic.php#127252) [¶](https://www.php.net/manual/en/language.constants.magic.php#127252)

**3 years ago**

`If PHP is run inside a web server request there is an important difference between the __DIR__ constant and $_SERVER['DOCUMENT_ROOT'].
Where __DIR__ of a PHP script contained within a sub-folder will include the complete server path $_SERVER['DOCUMENT_ROOT'] will contain a server path up to the _root_ of the application. This can be helpful when for instance an auto-loader is defined in an include file sitting inside a sub-folder and where the classes are located in another folder at the root of the application.`

[up](https://www.php.net/manual/vote-note.php?id=128655&page=language.constants.magic&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=128655&page=language.constants.magic&vote=down "Vote down!")

1


[**_Rich_**](https://www.php.net/manual/en/language.constants.magic.php#128655) [¶](https://www.php.net/manual/en/language.constants.magic.php#128655)

**2 years ago**

`<?php
namespace My\App {
class Api {
    public static fetch() {
      print __FUNCTION__ . "\n"; // outputs fetch
      print __METHOD__ . "\n"; // outputs My\App\Api::fetch
    }
}
Api::fetch();
}
namespace {
My\App\Api::fetch();
}
?>
__METHOD__ outputs a fully qualified method name; __FUNCTION__ when used in a method, outputs just the method name.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.constants.magic&repo=en&redirect=https://www.php.net/manual/en/language.constants.magic.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google