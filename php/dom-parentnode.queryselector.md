---
url: https://www.php.net/manual/en/dom-parentnode.queryselector.php
scraped_at: 2025-10-20T02:54:31.356Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Dom\\ParentNode::querySelector

(PHP 8 >= 8.4.0)

Dom\\ParentNode::querySelector — Returns the first element that matches the CSS selectors

### Description [¶](https://www.php.net/manual/en/dom-parentnode.queryselector.php\#refsect1-dom-parentnode.queryselector-description)

public**Dom\\ParentNode::querySelector**([string](https://www.php.net/manual/en/language.types.string.php) `$selectors`): [?](https://www.php.net/manual/en/language.types.null.php)[Dom\\Element](https://www.php.net/manual/en/class.dom-element.php)

Returns the first element that matches the CSS selectors specified
in `selectors`.


### Parameters [¶](https://www.php.net/manual/en/dom-parentnode.queryselector.php\#refsect1-dom-parentnode.queryselector-parameters)

`selectors`
A string containing one or more CSS selectors.


### Return Values [¶](https://www.php.net/manual/en/dom-parentnode.queryselector.php\#refsect1-dom-parentnode.queryselector-returnvalues)

Returns the first [Dom\\Element](https://www.php.net/manual/en/class.dom-element.php) that matches
`selectors`. Returns **`[null](https://www.php.net/manual/en/reserved.constants.php#constant.null)`** if no element matches.


### Errors/Exceptions [¶](https://www.php.net/manual/en/dom-parentnode.queryselector.php\#refsect1-dom-parentnode.queryselector-errors)

Throws a [DOMException](https://www.php.net/manual/en/class.domexception.php) with code
**`[Dom\\SYNTAX\_ERR](https://www.php.net/manual/en/dom.constants.php#constant.dom-syntax-err)`** when `selectors`
is not a valid CSS selector string.


### See Also [¶](https://www.php.net/manual/en/dom-parentnode.queryselector.php\#refsect1-dom-parentnode.queryselector-seealso)

- [Dom\\ParentNode::querySelectorAll()](https://www.php.net/manual/en/dom-parentnode.queryselectorall.php) \- Returns a collection of elements that match the CSS selectors

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/dom/dom/parentnode/queryselector.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdom-parentnode.queryselector%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=dom-parentnode.queryselector&repo=en&redirect=https://www.php.net/manual/en/dom-parentnode.queryselector.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google