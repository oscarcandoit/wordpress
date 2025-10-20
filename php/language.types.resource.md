---
url: https://www.php.net/manual/en/language.types.resource.php
scraped_at: 2025-10-20T02:31:27.507Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

## Resources [¶](https://www.php.net/manual/en/language.types.resource.php\#language.types.resource)

A [resource](https://www.php.net/manual/en/language.types.resource.php) is a special variable, holding a reference to an
external resource. Resources are created and used by special functions. See
the [appendix](https://www.php.net/manual/en/resource.php) for a listing of all these
functions and the corresponding [resource](https://www.php.net/manual/en/language.types.resource.php) types.


See also the [get\_resource\_type()](https://www.php.net/manual/en/function.get-resource-type.php) function.


### Converting to resource [¶](https://www.php.net/manual/en/language.types.resource.php\#language.types.resource.casting)

As [resource](https://www.php.net/manual/en/language.types.resource.php) variables hold special handles to opened files,
database connections, image canvas areas and the like, converting to a
[resource](https://www.php.net/manual/en/language.types.resource.php) makes no sense.


### Freeing resources [¶](https://www.php.net/manual/en/language.types.resource.php\#language.types.resource.self-destruct)

Thanks to the reference-counting system being part of Zend Engine,
a [resource](https://www.php.net/manual/en/language.types.resource.php) with no more references to it is detected
automatically, and it is freed by the garbage collector. For this reason, it
is rarely necessary to free the memory manually.


> **Note**:
>
> Persistent database links are an exception to this rule. They are
> _not_ destroyed by the garbage collector. See the
> [persistent\\
> connections](https://www.php.net/manual/en/features.persistent-connections.php) section for more information.

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/language/types/resource.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Flanguage.types.resource%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=language.types.resource&repo=en&redirect=https://www.php.net/manual/en/language.types.resource.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google