---
url: https://api.jquery.com/text/
scraped_at: 2025-10-20T03:17:17.495Z
---

## [jQuery API Documentation](https://jquery.com/ "jQuery API Documentation")

Navigation

Get the combined text contents of each element in the set of matched elements, including their descendants, or set the text contents of the matched elements.

#### Contents:

- [.text()](https://api.jquery.com/text/#text1)  - [.text()](https://api.jquery.com/text/#text)
- [.text( text )](https://api.jquery.com/text/#text2)  - [.text( text )](https://api.jquery.com/text/#text-text)
  - [.text( function )](https://api.jquery.com/text/#text-function)

## .text()Returns: [String](http://api.jquery.com/Types/\#String)

**Description:** Get the combined text contents of each element in the set of matched elements, including their descendants.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.text()](https://api.jquery.com/text/\#text)

  - This method does not accept any arguments.

Unlike the `.html()` method, `.text()` can be used in both XML and HTML documents. The result of the `.text()` method is a string containing the combined text of all matched elements. (Due to variations in the HTML parsers in different browsers, the text returned may vary in newlines and other white space.) Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The code `$( "div.demo-container" ).text()` would produce the following result:

`Demonstration Box list item 1 list item 2`

The `.text()` method should not be used on form inputs or scripts. To set or get the text value of `input` or `textarea` elements, use the [`.val()`](https://api.jquery.com/val/) method. To get the value of a script element, use the [`.html()`](https://api.jquery.com/html/) method.

As of jQuery 1.4, the `.text()` method returns the value of text and CDATA nodes as well as element nodes.

Find the text in the first paragraph (stripping out the html), then set the html of the last paragraph to show it is just text (the red bold is gone).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28 | ```<br>``` |

#### Demo:

## .text( text )Returns: [jQuery](http://api.jquery.com/Types/\#jQuery)

**Description:** Set the content of each element in the set of matched elements to the specified text.

- #### version added: [1.0](https://api.jquery.com/category/version/1.0/) [.text( text )](https://api.jquery.com/text/\#text-text)

  - **text**

    Type: [String](http://api.jquery.com/Types/#String) or [Number](http://api.jquery.com/Types/#Number) or [Boolean](http://api.jquery.com/Types/#Boolean)

    The text to set as the content of each matched element. When Number or Boolean is supplied, it will be converted to a String representation.
- #### version added: [1.4](https://api.jquery.com/category/version/1.4/) [.text( function )](https://api.jquery.com/text/\#text-function)

  - **function**

    Type: [Function](http://api.jquery.com/Types/#Function)( [Integer](http://api.jquery.com/Types/#Integer) index, [String](http://api.jquery.com/Types/#String) text )
     =>
     [String](http://api.jquery.com/Types/#String)

    A function returning the text content to set. Receives the index position of the element in the set and the old text value as arguments.

Unlike the `.html()` method, `.text()` can be used in both XML and HTML documents.

We need to be aware that this method escapes the string provided as necessary so that it will render correctly in HTML. To do so, it calls the DOM method `.createTextNode()`, does not interpret the string as HTML. Consider the following HTML:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7 | ```<br>``` |

The code `$( "div.demo-container" ).text( "<p>This is a test.</p>" );` will produce the following DOM output:

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

It will appear on a rendered page as though the tags were exposed, like this:

|     |     |
| --- | --- |
| 1 | ```<br>``` |

The `.text()` method should not be used on input elements. For input field text, use the [.val()](https://api.jquery.com/val/) method.

As of jQuery 1.4, the `.text()` method allows us to set the text content by passing in a function.

|     |     |
| --- | --- |
| 1<br>2<br>3 | ```<br>``` |

Given an unordered list with three `<li>` elements, this example will produce the following DOM output:

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5 | ```<br>``` |

Add text to the paragraph (notice the bold tag is escaped).

|     |     |
| --- | --- |
| 1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23 | ```<br>``` |

#### Demo: